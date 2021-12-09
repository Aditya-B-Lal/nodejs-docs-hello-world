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
                  sh 'docker build -t mypipeline .'
                }
            }
        }
        stage('Deploy Docker Image') {
            steps {
                script {
                 withCredentials([string(credentialsId: 'docker_pipeline', variable: 'dockerinput')]) {
                    sh 'docker login -u 9526584898 -p ${dockerinput}'
                 }  
                 sh 'docker push 9526584898/newpipeline:mypipeline'
                }
            }
        }
    }
}
