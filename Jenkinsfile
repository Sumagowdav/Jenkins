pipeline {
    agent any

    stages {
        stage(checkout){
            steps{
                 git branch: 'main', url: 'https://github.com/Sumagowdav/Jenkins.git'
            }
        }
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
post {
        always {
            script {
                def emailSubject
                def emailBody
                def recipientEmail
               
                if (currentBuild.result == "SUCCESS") {
                    emailSubject = "Pipeline Success: ${env.helloworld_latest} - Build #${env.BUILD_NUMBER}"
                    emailBody = "The pipeline run for ${env.helloworld_latest} - Build #${env.BUILD_NUMBER} was successful. You can view the details at ${env.BUILD_URL}"
                    recipientEmail = "sgowdruv@gmail.com"
                }
                else {
                    emailSubject = "Pipeline Failure: ${env.helloworld_latest} - Build #${env.BUILD_NUMBER}"
                    emailBody = "The pipeline run for ${env.helloworld_latest} - Build #${env.BUILD_NUMBER} has failed. You can view the details at ${env.BUILD_URL}"
                    recipientEmail = "sgowdruv@gmail.com"
                }

                emailext (
                    subject: emailSubject,
                    body: emailBody,
                    to: recipientEmail
                )
            }
        }
    }
