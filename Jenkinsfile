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
    }
}