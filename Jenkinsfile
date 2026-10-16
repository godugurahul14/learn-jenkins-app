pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                echo 'Bulid stage started'
                sh '''
                    node --version
                    npm --version
                    ls -la
                    npm ci
                    npm run build
                    ls -la
                    echo "Build stage completed"
                '''
            }
        }
    }
}