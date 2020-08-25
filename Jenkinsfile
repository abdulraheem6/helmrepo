pipeline {
  agent any
  stages {
    stage('helm chart') {
      parallel {
        stage('helm chart') {
          steps {
            sh '/usr/local/bin/helm list'
          }
        }

        stage('') {
          steps {
            sh '/usr/local/bin/helm repo list'
          }
        }

      }
    }

  }
}