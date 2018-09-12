pipeline {
        agent any
        stages {
        stage('Sonarqube analysis') {
    steps {
    script {
             scannerHome = tool 'SonarScanner';
        }
     withSonarQubeEnv('SonarQube 6.7.5') {
         sh "${scannerHome}/opt/sonar" 
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
