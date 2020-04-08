def notifyProductionDeploy(){
  def icons = [":unicorn_face:", ":beer:", ":bee:", ":man_dancing:",
    ":party_parrot:", ":ghost:", ":dancer:", ":scream_cat:"]
  def randomIndex = (new Random()).nextInt(icons.size())
  
  def message = "@here Build
  <${env.BUILD_URL}|${currentBuild.displayName}> " +
    "successfuly deployed to the production ${icons[randomIndex]}"
  
  slackSend(message: message, channel: '#assignment-6', color: 'good', token: 'token')
}


pipeline {
  agent any
  stages {
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
        
        notifyProductionDeploy()
      }
    }

  }
}
