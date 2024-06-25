pipeline{
    agent{
        docker{
            image 'node:18-alpine'
        }
    }
    stages{
        stage('Build'){
            steps{
                sh '''
                ls -la
                node version 
                npm ci
                npm run build 
                ls -la 
                npm version
                '''
            }
        }
        stage('Test'){
            steps{
                sh'''
            This is test stage 
            '''
            }
        }
    }
}