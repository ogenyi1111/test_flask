pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                script {
                    slackSend(color: '#439FE0', message: "📦 Stage: *Checkout Code* started.")
                }
                git branch: 'main', url: 'https://github.com/ogenyi1111/test_flask'
                script {
                    slackSend(color: '#36a64f', message: "✅ Stage: *Checkout Code* completed.")
                }
            }
        }
        stage('Build') {
            steps {
                script {
                    slackSend(color: '#439FE0', message: "🏗️ Stage: *Build* started.")
                }
                bat 'echo "Building the app"'
                script {
                    slackSend(color: '#36a64f', message: "✅ Stage: *Build* completed.")
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    slackSend(color: '#439FE0', message: "🧪 Stage: *Test* started.")
                }
                bat 'echo "Running tests"'
                script {
                    slackSend(color: '#36a64f', message: "✅ Stage: *Test* completed.")
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    slackSend(color: '#439FE0', message: "🚀 Stage: *Deploy* started.")
                }
                bat 'echo "Deploying"'
                script {
                    slackSend(color: '#36a64f', message: "✅ Stage: *Deploy* completed.")
                }
            }
        }
    }

    post {
        always {
            echo 'This will always run'
            slackSend(color: '#FFFF00', message: "🟡 Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' finished. Check: ${env.BUILD_URL}")
        }
        success {
            echo 'This will run only if successful'
            slackSend(color: '#00FF00', message: "✅ Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' succeeded!")
        }
        failure {
            echo 'This will run only if failed'
            slackSend(color: '#FF0000', message: "❌ Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' failed!")
        }
    }
}
