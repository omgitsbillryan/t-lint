pipeline {

  agent any

  stages {
    stage('Checkout Code') {
      steps {
        sh "echo 'starting it up!!!!'"
        checkout scm
      }
    }

    stage('Print stuff') {
      steps {
        echo 'Inside anotherbranch!!!'
        echo "the change id..... ${env.CHANGE_ID}"
        echo sh(script: 'env|sort', returnStdout: true)
      }
    }

    stage('Test if pull request') {
      steps {
        when { changeRequest() }
        echo "INSIDE A CHANGE REQUEST"
      }
    }

    stage('Donezo') {
      steps {
        sh "echo 'Donezo.'"
      }
    }
  }
}
