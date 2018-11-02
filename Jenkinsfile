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
                kubernetes {
      label 'slave'
      defaultContainer 'jnlp'
      yaml """
apiVersion: v1
kind: Pod
metadata:
labels:
  component: ci
spec:
  # Use service account that can deploy to all namespaces
  # serviceAccountName: cd-jenkins
  containers:
  - name: busybox
    image: busybox
    command:  
  - name: echo
    command:
    - echo "`ls /`"
"""
}
            }
            steps {
                echo 'app' 
                echo 'make check'
            }
        }
    }
}
