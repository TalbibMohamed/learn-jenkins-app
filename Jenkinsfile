pipeline {
    agent any

    stages {
        stage('Build') {
            agent{
                docker{
                    image "node:18-alpine"
                    reuseNode true 
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm set strict-ssl false
                    npm ci 
                    npm run build
                    ls -la 
                '''
            }
        }


    }
}