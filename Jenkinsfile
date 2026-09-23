pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
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
                    python app.py
                '''
            }
        }
    }
}