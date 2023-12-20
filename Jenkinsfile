pipeline {
    agent any

    environment {
        SONARQUBE_HOME = tool 'sonarqube';
        SCANNER_HOME = tool 'sonarscanner';
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout scm
                }
            }
        }

        stage('SonarQube Analysis') {
            steps {
                script {
                    withSonarQubeEnv('Your_SonarQube_Server_Name') {
                        // Set SonarQube project key and name
                        def projectKey = 'test-jenkins'
                        def projectName = 'test-jenkins'

                        // Run SonarScanner with project key
                        bat "${SCANNER_HOME}/bin/sonar-scanner -Dsonar.projectKey=${projectKey} -Dsonar.projectName=${projectName}"
                    }
                }
            }
        }
    }

    post {
        always {
            script {
                // Perform any additional post-processing steps here if needed
            }
        }
    }
}
