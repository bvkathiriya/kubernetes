pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/justmeandopensource/playjenkins.git'
      }
    }

    

    stage('Deploying into k8s'){
            steps{
                sh 'kubectl apply -f react-demo.yml'
                sh 'kubectl apply -f svc.yml'
            }
        }


  }

}
