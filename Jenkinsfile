 pipeline {
        agent any
    stages {
        stage("build & SonarQube analysis") {
        steps {
            withSonarQubeEnv('SonarQubedefault') {
                 bat 'mvn sonar:sonar'
                }
            }
        }
    }
 }