pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw clean'
        sh './mvnw compile'
      }
    }
    stage('Test') {
      steps {
        sh './mvnw test'  
      }
    }
    stage('Package') {
      steps {
        sh './mvnw package'
      }
    }
  }
}
