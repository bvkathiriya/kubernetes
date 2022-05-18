pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/justmeandopensource/playjenkins.git'
      }
    }

    

   stage('Deploy to K8s') {
      steps {
        withKubeConfig([credentialsId: 'kubernetes']) {
          sh 'kubectl apply -f react-demo.yaml'
          sh 'kubectl apply -f svc.yaml'
        }
      } 
    }


  }

}
