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
                    reuseNode true
                }
                
            }
            steps {
                echo 'Hello World From Docker'
                sh 'npm --version'
                sh 'ls -ltr'
                sh 'npm ci'
                sh 'npm run build'
                sh 'ls -ltr'
                //sh 'npm run build'
                sh 'echo "node.js is configured"'
            }
        }
        stage('Test The Build'){
            steps{
                 sh '''
                    cat ./build/index.html | tail -1
                    npm test -a
                    echo "All test cases are passed"
                  '''
            }
        }
    }
}
