pipeline{
  agent any
  stages{
    stage('Checkout Code'){
      steps{
        git branch: 'main', Url: 'https://github.com/ogenyi1111/test_flask'
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
