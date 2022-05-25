pipeline {
        agent any
    stages {
        stage("Build Stage")
        {
            steps
            {
                bat 'mvn clean install'
            }
        }
        stage("SonarQube analysis") 
        {
            steps
            {
                withSonarQubeEnv('SonarQubedefault')
                {
                    bat 'mvn sonar:sonar'
                }
            }
        }
 	stage("Quality Gate") {
            steps {
                timeout(time: 2, unit: 'MINUTES') {
                    // Parameter indicates whether to set pipeline to UNSTABLE if Quality Gate fails
                    // true = set pipeline to UNSTABLE, false = don't
                    waitForQualityGate abortPipeline: true
                }
            }
        }
        stage ('Deploy') {
            steps {
                script {
                    deploy adapters: [tomcat9(credentialsId: 'ApacheTomcatadmin', path: '', url: 'http://localhost:5000/')], contextPath: null, war: 'target/*.war'
                }
            }
        }
    }
}