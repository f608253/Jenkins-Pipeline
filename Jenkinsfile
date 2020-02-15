//node {
//    checkout scm
//}

pipeline {
          agent any 
          stages {
                stage('Build') {
                     steps {
					  timestamps {
                          echo "Building the code stage******kool*****sure*********"
                     }
                 }
				 }
                stage('Test') {
                     steps {
					 timestamps {
                           echo "Testing stage****************************"
                     }
					 }
                }
                stage('Deploy') {
                     steps {
					 timestamps {
                          echo "Deploying stage of code*********************"
			  sh 'echo "stage" > generatedFile.txt'   
                     }
                }
				}
           }
		   
//          emailext body: 'A Test email for the Job', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test email for Jenkins Engine'
          post {
        always {
            archiveArtifacts artifacts: 'generatedFile.txt', onlyIfSuccessful: true
            
            echo 'I will always say Hello again!'
                
            emailext attachLog: true, attachmentsPattern: 'generatedFile.txt',
                body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}\n More info at: ${env.BUILD_URL}",
                recipientProviders: [developers(), requestor()],
                subject: "Jenkins Build ${currentBuild.currentResult}: Job ${env.JOB_NAME}"
           
            }
        }       
}
