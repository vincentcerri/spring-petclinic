pipeline {
  agent any
  stages {
    stage('Start') {
      slackSend (color: '#FFFF00', message: "Build Started '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})" )
    }
    stage('Build') {
      steps {
        sh 'mvn clean'
        sh 'mvn compile'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }

  }
}
