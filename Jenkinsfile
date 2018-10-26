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
      slackSend (color: '#00FF00', message: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")

      hipchatSend (color: 'GREEN', notify: true,
          message: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})"
        )

      emailext (
          subject: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
          body: """<p>SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>
            <p>Check console output at &QUOT;<a href='${env.BUILD_URL}'>${env.JOB_NAME} [${env.BUILD_NUMBER}]</a>&QUOT;</p>""",
          recipientProviders: [[$class: 'DevelopersRecipientProvider']]
        )
    }
}       

}
