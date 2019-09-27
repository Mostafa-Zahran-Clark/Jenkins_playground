library ('base@JCLARK-51476')
pipeline {
    agent any
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
     stage('Fail'){
     steps{
     sh 'exit 1' 
     }
     }
    }
}
