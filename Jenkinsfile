library ('base@JCLARK-51476')
pipeline {
    agent {
    kubernetes {
      defaultContainer 'jnlp'
      yamlFile '.jenkins/backend.yaml'
    }
  }
    environment {
        QA_EMAIL_ON_FAILURE = "mostafa.zahran@clark.de"
    }
    post {
        failure {
            emailext(
          body: env.BUILD_URL, 
          to: env.QA_EMAIL_ON_FAILURE, 
          subject: "Build ${env.BUILD_NUMBER} Failed"
          )
      }
    }
    stages{
     stage('add ruby file'){
     steps{
     sh 'touch xx.rb'
     sh "xx.rb < echo puts('sss')"
     }
     }
     stage('execute it') {
     steps{
     sh 'ruby xx.rb'
     }
     }
    stage('delete it') {
     steps{
      sh 'rm xx.rb'
     }
     }
    }
}
