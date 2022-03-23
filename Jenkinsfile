pipeline{
    agent {
        docker {
            image 'node:16.14.2'
        }
    }
    environment {
        CI = 'true'
    }
    
    stages {
        stage('build') {
            steps {
                sh 'npm ci'
                sh 'npm run build'
                archiveArtifacts artifacts: 'build/'
            }
        }

        // stage('test') {
        //     steps {
        //         sh 'node test'
        //     }
        // }
        
        stage('deliver'){
            steps{
                sh 'npm install netlify-cli'
                sh 'npx netlify deploy --site $NETLIFY_SITE_ID --$NETLIFY_AUTH_TOKEN --dir build/ --prod'
            }
        }
    }
}