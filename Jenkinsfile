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
        echo sh(script: 'env|sort', returnStdout: true)
      }
    }

    // stage('Create virtualenv') {
    //   steps {
    //     sh 'virtualenv venv'
    //     sh 'venv/bin/python -m pip install -r requirements.txt'
    //   }
    // }

    // stage('Lint Ansible') {
    //   steps {
    //     script {
    //       locations   = ['*.yml'].join(' ')
    //       args        = '-p' // this file uses a non-existent module
    //       lint_output_file = 'ansible-lint.txt'
    //     }
    //     sh "bash -c 'source venv/bin/activate && ansible-lint ${args} ${locations} > ${lint_output_file} || true'"
    //   }
    //   post {
    //     always {
    //       script {
    //         quality_gate = (env.BRANCH_NAME == 'master') ? [] : [[threshold: 1, type: 'DELTA']]
    //       }
    //       recordIssues enabledForFailure: true, 
    //           blameDisabled: true,
    //           tool: ansibleLint(pattern: lint_output_file),
    //           referenceJobName: 'Testing/t-lint/master',
    //           qualityGates: quality_gate
    //     }
    //   }
    // }
    stage('Donezo') {
      steps {
        sh "echo 'Donezo.'"
      }
    }
  }
}
