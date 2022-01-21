pipeline {
  agent any

  options {
    timestamps()
    buildDiscarder logRotator(artifactDaysToKeepStr: '14', artifactNumToKeepStr: '100', daysToKeepStr: '60', numToKeepStr: '1000')
  }

  stages {

    stage ('Build') {
      steps {
        nodejs(nodeJSInstallationName: 'Node 16') {
          sh 'npm ci'
        }
      }
    }

    stage ('Run NPM') {
      steps {
        sh "npm start"
      }
    }
  }
}
