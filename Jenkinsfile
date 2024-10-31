pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code from GitHub...'
                git url: 'https://github.com/Sijo-K/my-web-app.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                echo 'No build step required for static HTML.'
            }
        }
        stage('Test') {
            steps {
                echo 'Running HTML validation...'
                // Install HTMLHint locally
                sh 'npm install htmlhint'
                // Run HTMLHint using npx
                sh 'npx htmlhint index.html'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging server...'
                // Replace the following command with your actual deployment logic
                // For example, you might use SCP to copy the index.html to a staging server
                // sh 'scp -r index.html user@staging-server:/path/to/deploy'
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
            // Any cleanup actions if necessary
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
