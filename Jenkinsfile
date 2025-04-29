pipeline { 
    agent any 
    
    environment {
        PATH = "/opt/maven/bin:$PATH"
    }
    
    stages {
        
        stage('Build') { 
            steps {
                sh 'mvn clean deploy'
            }
        }
        
        stage('SonarQube Analysis') { 
            environment {
                scannerHome = tool 'somu-sonar-scanner'    
            }
            steps {
                withSonarQubeEnv('somu-sonarqube-server') { 
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
        
    }
}



