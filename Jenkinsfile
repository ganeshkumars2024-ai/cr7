pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
            }
        }

        stage('Show Build Info') {
            steps {
                echo "BUILD NUMBER: ${env.BUILD_NUMBER}"
                echo "JOB NAME:     ${env.JOB_NAME}"
                echo "WORKSPACE:    ${env.WORKSPACE}"
            }
        }

        stage('Run Linter') {
            steps {
                echo "Installing flake8 if missing and running linter check..."
                // Ensures flake8 is installed on the agent before validating app.py
                bat "python -m pip install flake8"
                bat "python -m flake8 app.py"
            }
        }
    }
}
