pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/justmeandopensource/playjenkins.git'
      }
    }

    

    stage('K8S Deploy '){
            steps{
                sh kubernetesDeploy(configs:'react-demo.yml','svc.yaml',kubeconfigId:'kubernetes', enableConfigSubstitution:true)
                
            }
        }


  }

}
