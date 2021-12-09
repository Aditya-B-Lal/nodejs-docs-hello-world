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
                  sh 'docker build -t 9526584898/newpipeline .'
                }
            }
        }
        stage('Deploy Docker Image') {
            steps {
                script {
                 withCredentials([string(credentialsId: 'docker_pipeline', variable: 'dockerhubpwd')]){
                    sh 'docker login -u 9526584898 -p ${dockerhubpwd}'
                 }  
                 sh 'docker push 9526584898/newpipeline'
                }
            }
        }
    }
}
          
    
