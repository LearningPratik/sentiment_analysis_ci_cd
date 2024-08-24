pipeline {
  agent any 
      stages {
        stage('Clone repository') {
          /* CLoning repo to our workspace */
        steps {
          checkout scm
        }
      }

      stage('Build image') {
        steps {
          sh 'docker build -t sentiment-analysis:v1 .'
          }
      }

      stage('Run image') {
        steps {
          sh 'docker run -d -p 4000:4000 --name simple_sentiment_analysis sentiment-analysis:v1'
        }
      }

      stage('Testing') {
        steps {
          echo 'testing...'
        }
      }
    }
 }
