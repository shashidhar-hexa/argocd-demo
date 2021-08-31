pipeline {

  agent { label 'kubepod' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/hegdeshashi/argocd-demo.git', branch:'master'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "sandbox/ApplicationSet/application-prometheus.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}
