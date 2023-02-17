pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh 'make -C main'
            }
            post {
                failure {
                    echo 'Build stage failed'
                }
              }
            
        }

        stage('Test') {
            steps {
                sh './main/hello_exec'
            }
            post {
                failure {
                    echo 'Test stage failed'
                }
              }
        }


        stage('Cleanup') {
            steps {
                sh 'adarsh ./main/hello_exec'
            }
            post {
                failure {
                    echo 'Cleanup stage failed'
                }
              }
        }
    }
}
