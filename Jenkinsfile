 pipeline {
        agent none
        stages {
          stage("build & SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv('SonarQubedefault') {
                bat 'mvn clean package sonar:sonar'
              }
            }
          }
        }
 }