pipeline {
    agent none
    stages {
        stage('build') {
            agent any
            steps {
                sh 'echo Success'
            }
        }
        stage('Test on Linux') {
            agent { 
                label 'linux'
            }
            steps {
                echo 'app' 
                echo 'make check'
            }
            post {
                always {
                    junit '**/target/*.xml'
                }
            }
        }
    }
}
