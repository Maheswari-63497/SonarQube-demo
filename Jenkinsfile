pipeline{
    agent any
    tools {
        maven 'Maven' 
    }
    /*stages {
        stage('Quality Gate Status check'){
            steps {
                    withSonarQubeEvn(installationName:'SonarQubedefault', credentialsId: 'SonarQube-admin') {
                        bat "sonar:sonar"
                    }
                        timeout(time:1, unit:'HOURS') {
                            def dg =waitForQualityGate()
                            if(dg.status !='OK'){
                                    error "Pipeline aborted due to quality gate failure"
                            }
                        }
                    bat "mvn clean install"
                }
        }
    }*/

    stages {
        stage('Quality Gate Status check'){
           steps {
                /*script{*/
                   /* withSonarQubeEnv('SonarQubedefault') {
                        bat "sonar:sonar"
                    }
                    timeout(time:1, unit:'HOURS') {
                        def dg =waitForQualityGate()
                        if(dg.status !='OK'){
                            error "Pipeline aborted due to quality gate failure"
                        }
                    }*/
                    bat "mvn clean install"
                    bat "mvn sonar:sonar"
               /* }*/
           }
        }
    }
}