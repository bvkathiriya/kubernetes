pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/justmeandopensource/playjenkins.git'
      }
    }

    

    stage('Deploy App to Kubernetes') {     
      steps {
        container('kubectl') {
          withCredentials([file(credentialsId: 'kubernetes', variable: 'KUBECONFIG')]) {
          #  sh 'sed -i "s/<TAG>/${BUILD_NUMBER}/" myweb.yaml'
            sh 'kubectl apply -f react-demo.yaml'
            sh 'kubectl apply -f svc.yaml'
          }
        }
      }
    }

  }

}
