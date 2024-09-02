pipeline {
    agent any
    
    stages {
        stage('Login to Docker'){
            steps {
              sh 'docker login --username adityafedex --password Aditya@123'  
            }
        }
        stage('with docker') {
            agent{
                docker{
                    image 'node:18-alpine'
                }
                
            }
            steps {
                sh '''
                echo 'Hello World From Docker'
                npm --version
                echo "node.js is configured"
                echo "Welcome to Jenkins workd guru!!"
                '''
                
            }
        }
    }
}
