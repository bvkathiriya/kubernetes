pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/justmeandopensource/playjenkins.git'
      }
    }

    

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "react-demo.yaml", "svc.yaml", kubeconfigId: "kubernetes")
        }
      }
    }

  }

}
