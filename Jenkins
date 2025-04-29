pipeline {
   agent any
   environment {
       PATH="/opt/maven/bin:$PATH"
   }
   stages {
       stage('git clone') {
           steps {
              git url: "https://github.com/somu123456789/war-web-project.git", branch:'master'
           }
       }
       stage('build'){
          steps {
            sh 'mvn clean install'
          }
       }
   }
}
