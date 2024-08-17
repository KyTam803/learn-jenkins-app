pipeline {
    agent any
    
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

       stage('Check for existence of index.html') {
           agent{
               steps{
                 script{
                  if (fileExists('learn-jenkins-app/public/index.html')) {
                      echo "File learn-jenkins-app/public/index.html found!"
                     }
                  }
              } 
           }              
       }
        
   }
}
