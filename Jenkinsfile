pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'starting our pipeline'
          }
        }

        stage('Test') {
          steps {
            echo 'testing our app'
          }
        }

      }
    }

    stage('Deployment') {
      steps {
        echo 'Deploying to AWS'
      }
    }

  }
}