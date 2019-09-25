library ('base@JCLARK-51476')
pipeline {
    agent any
    environment {
        QA_EMAIL_ON_FAILURE = "mostafa.zahran@clark.de, guilherme.henrique@clark.de"
    }
    post {
        failure {
            emailext(
          body: 'A Test EMail', 
          to: env.QA_EMAIL_ON_FAILURE, 
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
