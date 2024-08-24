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
          script {
            try {
            docker.build('sentiment-analysis:v1 .')
            } catch (Exception e) {
               echo "Caught: ${e}"
               error "Failed to build Docker image"
            }
          }
        }
      }

      stage('Run image') {
        steps {
          script {
            docker.run('-d -p 4000:4000 --name simple_sentiment_analysis sentiment-analysis:v1')
           }
        }
    }

      stage('Testing') {
        steps {
          echo 'testing...'
        }
      }
    }
 }
