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
       /* stage("SonarQube analysis") 
        {
            steps
            {
                withSonarQubeEnv('SonarQubedefault')
                {
                    bat 'mvn sonar:sonar'
                }
            }
        }
        stage ('Deploy') {
            steps {
                script {
                    deploy adapters: [tomcat9(credentialsId: 'ApacheTomcatadmin', path: '', url: 'http://localhost:5000/')], contextPath: null, war: 'target/*.war'
                }
            }
        }*/
    }
}