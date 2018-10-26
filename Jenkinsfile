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
    success {
          message: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})"
    }
}       

}
