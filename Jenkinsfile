pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Compile') {
            steps {
                sh 'g++ -o hello_world main.cpp'
            }
        }

        stage('Test') {
            steps {
                sh './hello_world'
            }
        }

        stage('Cleanup') {
            steps {
                sh 'rm hello_world'
            }
        }
    }
}
