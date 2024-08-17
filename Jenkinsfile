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
                   sh 'npm test'
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
               steps{
                   script{
                      if(fileExists('learn-jenkins-app/public/index.html')){
                   }
                   echo "file exists"
               }  
             }
           }
        
     
    
  }       
}
    
