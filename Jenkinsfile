pipeline{
    agent {
        docker {
            image 'node:16.14.2'
            args '-p 3000:3000'
        }
    }
    // environment {
    //     CI = 'true'
    // }
    stages {
        stage('build'){
            steps{
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('test'){
            steps{
                sh 'npm run test'
            }
        }
        stage('deliver'){
            steps{
                sh 'npm start'
            }
        }
    }
}