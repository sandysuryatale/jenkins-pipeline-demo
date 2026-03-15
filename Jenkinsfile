pipeline{
    agent any
    environment {
        APP_NAME = "demo-app"
    }
    stages {
      stage('Checkout') {
        steps{
          echo "checking out code from github"
          checkout scm
        }
      }
      stage('Build') {
          steps {
              echo "Building ${APP_NAME}"
              sh '''
               echo "Stimulating Build..."
               sleep 2
               '''
            }
      }
      stage('test') {
        steps {
              echo "Running tests"
              sh '''
               echo "Stimulating Build..."
               sleep 2
               '''
            }
      }
      stage('Deploy') {
        when {
          branch 'main'
        }
        steps {
              echo "Deploying ${APP_NAME} "
              sh '''
               echo "Deploying successful..."
               sleep 2
               '''
            }
      post {
        successs {
           echo "pipeline completed successful"
        }
        failure {
           echo "pipeline failed"
        }
        always {
           echo "pipeline finished"
        }
      }
      }
    }
}
