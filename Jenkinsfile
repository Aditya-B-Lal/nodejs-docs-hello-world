pipeline {
    agent any
    
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
         stage('Build Docker Image') {
            steps {
                script {
                  sh 'docker pull postgres'
                }
            }
        }
        
        stage('Deploy Docker Image') {
            steps {
                script {
                     
                    sh 'docker login -u 9526584898 -p Aditya123*'
                    sh 'docker tag postgres 9526584898/latest:postgres'
                    sh 'docker push 9526584898/latest:postgres'
                }
            }
        }
    }
}
