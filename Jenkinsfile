pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Simulating build step...'
                // Uncomment below to simulate a failure:
                // error 'Forcing a failure for testing'
            }
        }
    }

    post {
        success {
            emailext subject: "✅ SUCCESS: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                     body: "The build succeeded.\n\nCheck it: ${env.BUILD_URL}",
                     to: "monicashivaraju@gmail.com"
        }
        failure {
            emailext subject: "❌ FAILURE: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                     body: "The build failed.\n\nCheck it: ${env.BUILD_URL}",
                     to: "monicashivaraju@gmail.com"
        }
    }
}
