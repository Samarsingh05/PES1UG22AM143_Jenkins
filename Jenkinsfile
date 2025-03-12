pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Samarsingh05/PES1UG22AM143_Jenkins.git'
            }
        }

        stage('Build') {
            steps {
                sh 'g++ -o PES1UG22AM143-1 working.cpp'
            }
        }

        stage('Test') {
            steps {
                sh './PES1UG22AM143-1'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                git config --global user.email "2003singhsamar@example.com"
                git config --global user.name "Samar Singh"
                git add working.cpp
                git commit -m "Updated working C++ file"
                git push origin main
                '''
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
