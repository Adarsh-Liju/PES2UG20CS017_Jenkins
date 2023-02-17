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


        stage('Deploy') {
            steps {
                sh 'git add ./main/hello_exec'
                sh 'git commit -m "Deployed to github"'
                sh 'git push'
            }
            post {
                failure {
                    echo 'Cleanup stage failed'
                }
              }
        }
    }
}
