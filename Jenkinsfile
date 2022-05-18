pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/justmeandopensource/playjenkins.git'
      }
    }

    

   stage('Apply Kubernetes files') {
    withKubeConfig([credentialsId: 'kubernetes', serverUrl: 'http://127.0.0.1:34047/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/#/workloads?namespace=default']) {
      sh 'kubectl apply -f react-demo.yaml'
      sh 'kubectl apply -f svc.yaml'
    }
  }


  }

}
