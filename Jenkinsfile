node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'sonarscanner';
    withSonarQubeEnv() {
      bat "${scannerHome}/bin/sonar-scanner"
    }
  }
}
