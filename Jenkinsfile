pipeline {
  agent ()
  environment {
    dockerregname = ""
    dockerhubcred = ""

  }

  stages {
    stage ("Git Checkout") {
      checkout scm
    }
    stage ("Building Docker Image") {
      steps {
        sh 'docker build -f example2/Dockerfile -t rameshthangaraj/pytest01:latest'

      }
    }

    stage ("Push Images to Docker registry") {
      when {
        branch 'main'
      }
      steps {
        withDockerRegistry (url: "https://index.docker.io/v1/" , credntialsId: "dockerhubcred") {
          sh 'docker push rameshthangaraj/pytest01:latest'
          
        }
      }
    }
  }
}
