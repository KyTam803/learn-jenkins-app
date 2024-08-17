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

        stage('Test Stage') {
           steps {
               echo 'Testing Stage'
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
        }
    }
}
