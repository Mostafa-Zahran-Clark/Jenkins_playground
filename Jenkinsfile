library ('base@JCLARK-51476')
pipeline {
    agent any
    environment {
        QA_EMAIL_ON_FAILURE = "mostafa.zahran@clark.de"
    }
    post {
        failure {
            emailext(
          body: 'A Test EMail', 
          recipientProviders: env.QA_EMAIL_ON_FAILURE.split(","), 
          subject: 'Test'
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
