pipeline {
        agent any
        stages {
        stage('Build') {  
            steps {
             sh  'mvn clean install'
            node {
  stage('SCM') {
    git 'https://github.com/balaji-tkr/Hello-App02.git'
  }
  stage('SonarQube analysis') {
    // requires SonarQube Scanner 2.8+
    def scannerHome = tool 'SonarQube Scanner 6.7.5';
    withSonarQubeEnv('My SonarQube Server') {
      sh "${scannerHome}/opt/sonar"
    }
  }
}
            }
        }
    }
 }
