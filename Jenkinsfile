pipeline {
        agent any
        stages {
         stage('Build') {  
            steps {
             sh  'mvn clean install'
            }
        }
                node {
  stage('SCM') {
    git 'https://github.com/balaji-tkr/Hello-App02'
  }
  stage('SonarQube analysis') {
    // requires SonarQube Scanner 2.8+
    def scannerHome = tool 'sonar-scanner-3.2.0.1227-linux';
    withSonarQubeEnv('server') {
      sh "${scannerHome}/opt/sonar/lib/scanner"
    }
  }
}
    }
 }
