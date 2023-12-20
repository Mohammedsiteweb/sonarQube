pipeline {
    agent none
    stages {
        stage("Build & SonarQube Scanner") {
            agent {
                label 'sonar'
            }
            steps {
                withSonarQubeEnv('sonar') {
                    script {
                        def projectKey = 'test-jenkins'
                        def projectName = 'test-jenkins'
                        bat 'mvn clean package sonar:sonar'
                    }
                }
            }
        }
    }
}
