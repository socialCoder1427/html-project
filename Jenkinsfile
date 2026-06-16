pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Repository Downloaded'
            }
        }

        stage('Build') {
            steps {
                bat 'dir'
            }
        }

        stage('Test') {
            steps {
                bat '''
                if exist index.html (
                    echo HTML File Found
                ) else (
                    exit /b 1
                )
                '''
            }
        }

        stage('Deploy') {
            steps {
                bat '''
                if not exist C:\\website mkdir C:\\website

                copy /Y index.html C:\\website\\index.html

                echo Deployment Successful
                '''
            }
        }
    }

    post {
        success {
            echo 'Pipeline Executed Successfully'
        }

        failure {
            echo 'Pipeline Failed'
        }
    }
}
