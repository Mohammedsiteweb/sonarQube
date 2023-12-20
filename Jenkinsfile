pipeline {
    agent none
    stages {
        stage("Build & SonarQube Scanner") {
            agent {
                label 'sonar'
            }
            steps {
                withSonarQubeEnv('SonarQube') {
                    script {
                        bat 'mvn clean package sonar:sonar'
                    }
                }
            }
        }
    }
}
