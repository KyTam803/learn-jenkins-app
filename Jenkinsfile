pipeline {
    agent any
    
    environment{
        my_file=fileExist 'learn-jenkins-app/public/index.html'
    }
    
    stages {
        stage('Build') {
            agent {
              docker {
                  image 'node:18'
                  reuseNode true
              }
          }       
            
          steps {
                sh '''
                   ls -la
                   node --version
                   npm --version
                   npm ci
                   npm run build
                   ls -la
           
                   '''
              }
        }
        
         stage('Testing Stage'){
           steps {
             echo 'Testing Stage'
         }
       }                 

       stage('Check if exists') {
             when { expression {my_file== 'true'}}
               steps{
                   echo "file exists"
               }  
             }
        
      stage('conditional if not exist'){
          when {expression {my_file =='false'}}
          steps {
              echo "File Exist"
          }        
    }
  }       
}
    
