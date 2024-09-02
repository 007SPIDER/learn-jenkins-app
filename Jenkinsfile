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
                    reuseNone true
                }
                
            }
            steps {
                echo 'Hello World From Docker'
                sh 'npm --version'
                sh 'ls -ltr'
                //sh 'npm run build'
                sh 'echo "node.js is configured"'
            }
        }
    }
}
