pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/ogenyi1111/test_flask'
            }
        }
        stage('Build') {
            steps {
                bat 'echo "Building the app"'
            }
        }
        stage('Test') {
            steps {
                bat 'echo "Running tests"'
            }
        }
        stage('Deploy') {
            steps {
                bat 'echo "Deploying"'
            }
        }
    }

    post {
        always {
            echo 'This will always run'
            slackSend (color: '#FFFF00', message: "Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' finished. Check console for details: ${env.BUILD_URL}")
        }
        success {
            echo 'This will run only if successful'
            slackSend (color: '#00FF00', message: "✅ Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' succeeded!")
        }
        failure {
            echo 'This will run only if failed'
            slackSend (color: '#FF0000', message: "❌ Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' failed!")
        }
    }
}
