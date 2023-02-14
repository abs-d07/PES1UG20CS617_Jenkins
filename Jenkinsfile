pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ -o output_file new_working.cpp'
                build job : 'PES1UG20CS617-1'
                echo 'Build Stage Successful'
            }
        }
        stage('Test') {
            steps {
                sh './output_file'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deployment Successful'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
