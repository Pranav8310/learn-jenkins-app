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
                npm version 
                npm ci
                npm build 
                ls -la 
                npm version
                '''
            }
        }
        stage('Test'){
            sh'''
            echo 'test stage
            '''
        }
    }
}