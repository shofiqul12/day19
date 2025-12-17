pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building the project..."
                // Simulating build step
                sh 'echo Hello World'
            }
        }
        stage('Test') {
            steps {
                echo "Running tests..."
                // Simulating test step
                sh 'exit 0' // Change to 'exit 1' to test failure notification
            }
        }
    }

    post {
        success {
            slackSend(
                channel: 'C0A4GGZ541F', 
                message: "✅ SUCCESS: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' completed successfully!\n${env.BUILD_URL}",
                color: '#36a64f'
            )
        }
        failure {
            slackSend(
                channel: 'C0A4GGZ541F', 
                message: "❌ FAILURE: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' failed!\n${env.BUILD_URL}",
                color: '#ff0000'
            )
        }
    }
}
