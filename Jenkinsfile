pipeline {
  agent any
  stages {
    stage('Build Demo App') {
      when {
        expression {
          params.REQUESTED_ACTION == 'Build'
        }

      }
      steps {
        sh 'npm install'
      }
    }
    stage('test') {
      steps {
        sh 'npm test'
      }
    }
    stage('create folder') {
      steps {
        sh 'mkdir files'
      }
    }
    stage('add file') {
      steps {
        sh 'npm run build'
      }
    }
  }
  parameters {
    choice(name: 'REQUESTED_ACTION', choices: '''Build
''', description: 'Type of action to perform')
  }
}