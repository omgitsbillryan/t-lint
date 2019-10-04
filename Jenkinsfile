pipeline {

  agent any

  environment {
    THE_BRANCH = env.BRANCH_NAME
  }

  stages {
    stage('Checkout Code') {
      steps {
        checkout scm
      }
    }

    stage('Print stuff') {
      steps {
        echo "the change id..... ${env.CHANGE_ID}"
        echo "BRANCH_NAME....... ${env.BRANCH_NAME}"
        echo "THE_BRANCH........ ${env.THE_BRANCH}"
        echo sh(script: 'env|sort', returnStdout: true)
      }
    }

    stage('Test if pull request') {
      when { changeRequest() }

      steps {
        echo "INSIDE A CHANGE REQUEST"
      }
    }

    stage('Run for branch master') {
      when { branch 'master' }

      steps {
        echo "MASTER BRANCH YO"
      }
    }

    stage('Run for NOT branch master') {
      when { not { branch 'master' } }

      steps {
        echo "NOT MASTER!!!!"
      }
    }

    stage('Donezo') {
      steps {
        sh "echo 'Donezo.'"
      }
    }
  }
}
