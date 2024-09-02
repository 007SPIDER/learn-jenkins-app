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
                echo 'Hello World From Docker'
                sh 'npm --version'
                sh 'echo "node.js is configured"'
            }
        }
        stage('Build App'){
            steps {
                sh '''
                    npm run build
                '''
            }
        }
    }
}
