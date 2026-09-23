pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
           text
Hello, Jenkins!
``` }
        }

        stage('Show Build Info') {
            steps {
                bat '''
                    echo BUILD_NUMBER=%BUILD_NUMBER%
                    echo JOB_NAME=%JOB_NAME%
                    echo WORKSPACE=%WORKSPACE%
                '''
            }
        }

        stage('Run Linter') {
            steps {
                bat '''
                    python -m pip install -r requirements.txt
                    python -m flake8 app.py
                '''
            }
        }

        stage('Run Application') {
            steps {
                bat 'python app.py'
            }
        }
    }
}