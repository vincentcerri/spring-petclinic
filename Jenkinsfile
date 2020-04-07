pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw clean'
        sh './mvnw compile'
        sh './mvnw test'
        sh './mvnw package'
      }
    }

  }
}
