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
                echo 'Running tests...'
                // Add any testing steps if applicable
                // For example, use a command-line tool to check for HTML errors, if desired.
                // sh 'npm install -g htmlhint && htmlhint index.html'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging server...'
                // Add your deployment logic here
                // For example, copying files to a staging server:
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
