pipeline {
          agent any 
          stages {
                stage('Build') {
                     steps {
                          echo "Building the code stage******kool*****sure*********"
                     }
                 }
                stage('Test') {
                     steps {
                           echo "Testing stage****************************"
                     }
                }
                stage('Deploy') {
                     steps {
                          echo "Deploying stage of code*********************"
                     }
                }
           }
post {
    always {
          emailext body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
    }
}       

}
