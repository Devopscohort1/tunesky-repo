pipeline {
    agent any

    environment {
        NODE_ENV = 'development'
    }
    tools {
        nodejs 'NodeJs 21.2.0'
    }
    stages{
        stage('clone repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Devopscohort1/tunesky-repo.git'
            }
        }
        stage('install dependencies') {
            steps {
            sh 'npm install'
            }
        } 
        stage( 'run test') {
            steps {
                sh ' npm run test'
            }
        }
        stage('Build test'){
            steps {
                sh 'npm run build'
            }
        }
    }
    post {
        success {
            echo 'successful'
        }
        failure {
            echo 'failed!'
        }
    }
}
