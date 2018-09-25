pipeline {
        agent any
        stages {
                stage('SCM')
                {
                        git 'https://github.com/balaji-tkr/sonarqube.git'
                }
                stage('mvn install')
                {
    def scannerHome = tool 'sonar-scanner-3.2.0.1227-linux';
    withSonarQubeEnv('sonarqube')
    {
      sh "${scannerHome}/opt/sonarqube/sonar-scanner-3.2.0.1227-linux/bin/sonar-scanner"
    }
  }
}
         stage('Build') {  
            steps {
             sh  'mvn clean install'
          
            }
        }
    }
 }
