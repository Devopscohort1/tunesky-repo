pipeline {
    agent any

    environment {
        NODE_ENV = 'development'
    }

    tools {
        maven "MAVEN3.9"
    } 
    stages {

        stage('Clone repository') {
        steps {
            git branch: 'main', url: 'https://github.com/Devopscohort1/tunesky-repo.git'
            }
        }
   
    stage('unit Test') {
        steps {
            dir('my-app') {      // Replace 'my-app' with your actual folder
            sh 'mvn test'
            }
        }
    }

    stage('Build') {
        steps {
            dir('my-app') {
            sh 'mvn install'
            }
            }
        }
    
    }
    post {
        success {
            echo 'CI pipeline completed successfully.'
        }
        failure {
            echo 'CI pipeline failed!'
        }

    }
}
