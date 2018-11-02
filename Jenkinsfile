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
            agent kubernetes
            steps {
                echo 'app' 
                echo 'make check'
            }
        }
    }
}
