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
                if not exist D:\\website mkdir D:\\website

                copy /Y index.html D:\\website\\index.html

                dir D:\\website
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment Successful'
        }
        failure {
            echo 'Deployment Failed'
        }
    }
}
