
pipeline {
    agent any
    stages {

        stage('Build') {
            steps {
                // Build your project, assuming you use Maven
                sh 'mvn clean package'
            }
        }
    }

    post {
        success {
            // Send email notification on success
            emailext (
                subject: 'Build Successful: ${env.JOB_NAME} [${env.BUILD_NUMBER}]',
                body: 'Good news! The build was successful.',
                to: 'ggaurav173@gmail.com'
            )
        }
        failure {
            // Send email notification on failure
            emailext (
                subject: 'Build Failed: ${env.JOB_NAME} [${env.BUILD_NUMBER}]',
                body: 'Bad news! The build failed.',
                to: 'your-email@example.com'
            )
        }
    }
}
