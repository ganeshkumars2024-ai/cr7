pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                // In production, this would be 'checkout scm'
            }
        }

        stage('Show Build Info') {
            steps {
                // Printing Jenkins environment variables
                echo "BUILD NUMBER: ${env.BUILD_NUMBER}"
                echo "JOB NAME:     ${env.JOB_NAME}"
                echo "WORKSPACE:    ${env.WORKSPACE}"
            }
        }

        stage('Run Linter') {
            steps {
                echo "Running flake8 linter check on app.py..."
                // Use 'sh' instead of 'bat' if your agent is Linux
                bat "python -m flake8 app.py"
            }
        }
    }
}
