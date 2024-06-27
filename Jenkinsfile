pipeline{
    agent any 

    stages{
        // stage('Build'){
        //     steps{
        //         sh '''
        //         ls -la
        //         npm version 
        //         npm ci
        //         npm run build 
        //         ls -la 
        //         npm version
        //         '''
        //     }
        // }
        stage('Test'){
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps{
                echo 'This is test stage'
            }
        }
        stage('E2E'){
            agent{
                docker{
                    'image mcr.microsoft.com/playwright:v1.45.0-jammy'
                    reuseNode true
                }
            }
            
            steps{
                sh '''
                    npm install -g serve
                    node_modules/.bin/serve -s build
                    npx playwright test
                '''
            }
        }
    }
}