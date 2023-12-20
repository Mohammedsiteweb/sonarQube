node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'sonarscanner';
    withSonarQubeEnv() {
      def projectKey = 'test-jenkins'
      def projectName = 'test-jenkins'
      bat "${scannerHome}/bin/sonar-scanner"
    }
  }
}
