pipeline{
    agent any
    tools {
        maven 'Maven' 
    }
    stages {
        stage('Quality Gate Status check'){
            steps {
                script {
                    withSonarQubeEvn('SonarQubedefault') {
                        sh "sonar:sonar"
                    }
                        /*timeout(time:1, unit:'HOURS') {
                            def dg =waitForQualityGate()
                            if(dg.status !='OK'){
                                    error "Pipeline aborted due to quality gate failure"
                            }
                        }*/
                    sh "mvn clean install"
                }
            }
        }
    }
}