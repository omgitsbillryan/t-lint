pipeline {

  agent any

  stages {
    stage('Checkout Code') {
      steps {
        checkout scm
      }
    }

    stage('Print stuff') {
      steps {
        echo 'Inside branch3'
        echo "the change id..... ${env.CHANGE_ID}"
        echo "BRANCH_NAME....... ${env.BRANCH_NAME}"
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

    stage('Check stuff') {
      when {
        anyOf {
          branch 'master'
          branch 'branch5'
        }
      }

      steps {
        echo "Inside branch master or branch5"
      }    
    }

    stage('Donezo') {
      steps {
        sh "echo 'Donezo.'"
      }
    }
  }
}
