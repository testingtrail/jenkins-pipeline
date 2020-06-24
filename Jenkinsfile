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
            echo "Chromedriver path is ${chromeDriverPath}"
          }
        }

      }
    }

    stage('Deployment') {
      steps {
        input(message: 'Quieres deployar?', id: 'OK')
        echo 'Deployed to AWS'
      }
    }

  }
  environment {
    chromeDriverPath = '/Users/jorge.quiros/qa/jenkinsPipeline'
  }
}