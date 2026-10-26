
pipeline {
    agent { label 'kali' }

    stages {
        stage('Build') {
            steps {
                echo 'Starting build...'
                sh 'echo "Building website..."'
                sh 'ls -la website/'
                echo 'Build completed!'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing website...'

                sh '''
                    test -f website/index.html
                    test -f website/style.css
                    test -f website/script.js
                '''

                echo 'All tests passed!'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Starting deployment...'
                sh 'whoami'
                echo 'Deploy completed!'
            }
        }
    }

    post {
        success {
            echo 'Pipeline successfully completed!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}

