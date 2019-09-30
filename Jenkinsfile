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
        echo 'Inside testbranch'
        echo "the change id..... ${env.CHANGE_ID}"
        echo sh(script: 'env|sort', returnStdout: true)
      }
    }

    stage('Donezo') {
      steps {
        sh "echo 'Donezo.'"
      }
    }
  }
}
