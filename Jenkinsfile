node {
    checkout scm
}

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
          emailext body: 'A Test email for the Job', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test email for Jenkins Engine'
    }
}       

}

/**
 * A Class description
 */
class Person {
    /** the name of the person */
    String name

    /**
     * Creates a greeting method for a certain person.
     *
     * @param otherPerson the person to greet
     * @return a greeting message
     */
    String greet(String otherPerson) {
       "Hello ${otherPerson}"
    }
}
