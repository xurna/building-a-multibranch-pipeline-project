pipeline {
    agent {
      docker {
        image 'node:6-alpine'
        args '-p 3000:3000'
      }
    }
    environment { 
      HOME="."
      CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install --unsafe-perm --allow-root'
            }
        }
        stage('Test') {
          steps {
            sh './jenkins/scripts/test.sh'
          }
        }
    }
}
