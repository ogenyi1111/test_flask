pipeline{
  agent any
  stages{
    stage('Checkout Code'){
      steps{
        git branch: 'main', url: 'https://github.com/ogenyi1111/test_flask'
      }
    }
    stage('Build'){
      steps{
        bat 'echo "Building the app"'
      }
    }
    stage('Test'){
      steps{
        bat 'echo "Running tests"'
      }
    }
      stage('Deploy'){
      steps{
        bat 'echo "Deploying"'
      }
    }
  }
}
post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
    }
}
