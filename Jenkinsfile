pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
                sh 'g++ -o output_file input_file.cpp'
                echo 'Build Stage Successful'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
                sh './output_file'
                echo 'Test Stage Successful'
            }
        }
        stage('Deploy') {
            steps {
                sh 'mvn deploy'
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
