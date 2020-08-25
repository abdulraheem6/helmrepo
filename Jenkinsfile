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

    stage('helminstall') {
      parallel {
        stage('helminstall') {
          steps {
            sh 'helm install blue-ocean-helm mystable/testchart'
            unstable 'stable'
          }
        }

        stage('bypass') {
          steps {
            echo 'hello'
          }
        }

      }
    }

    stage('test') {
      steps {
        sh 'curl http://127.0.0.1:8080'
      }
    }

  }
}