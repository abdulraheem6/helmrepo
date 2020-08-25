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

        stage('error') {
          steps {
            sh '/usr/local/bin/helm repo list'
          }
        }

      }
    }

    stage('adding repo') {
      steps {
        sh '/usr/local/bin/helm repo add stable https://kubernetes-charts.storage.googleapis.com'
      }
    }

    stage('helmcreate') {
      steps {
        sh 'mkdir mystable;helm create mystable/testchart'
      }
    }

  }
}