pipeline{
    agent {
        docker {
            image 'node:16.14.2'
            args '-p 3002:3002'
        }
    }
    environment {
        CI = 'true'
    }
    
    stages {
        stage('build') {
            steps {
                sh 'npm install'
                //sh 'npm run build'
            }
        }

        // stage('test') {
        //     steps {
        //         sh 'npm run test'
        //     }
        // }
        
        stage('deliver'){
            steps{
                sh 'npm start'
                sh 'npm run build'
            }
        }
    }
}