pipeline {
        agent any
        stages {
        stage('Sonarqube analysis') {
    steps {
    script {
             scannerHome = tool 'sonar-scanner';
        }
     withSonarQubeEnv('SonarQube 6.7.5') {
         sh "${scannerHome}/opt/sonar-scanner-3.2.0.1227-linux" 
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
