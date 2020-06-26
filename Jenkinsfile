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

        stage('Test.Log') {
          steps {
            writeFile(file: 'LogFile.txt', text: 'This is a log file. The driver path is ${chromeDriverPath}')
          }
        }

      }
    }

    stage('Deployment') {
      parallel {
        stage('Deployment') {
          steps {
            input(message: 'Quieres deployar?', id: 'OK')
            echo 'Deployed to AWS'
          }
        }

        stage('Artifacts') {
          steps {
            archiveArtifacts 'LogFile.txt'
          }
        }

      }
    }

  }
  environment {
    chromeDriverPath = '/Users/jorge.quiros/qa/jenkinsPipeline'
  }
}