 pipeline {
        agent none
        stages {
          stage("build & SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv('SonarQubedefault') {
                sh 'mvn clean package sonar:sonar'
              }
            }
          }
        }
      }