pipeline {
    agent any

    environment {
        NODE_ENV = 'development'
    }

    tools {
       nodejs 'NodeJS-18'
    } 
    stages {

        stage('Clone repository') {
        steps {
            git branch: 'main', url: 'https://github.com/Devopscohort1/tunesky-repo.git'
            }
        }
   
    stage('unit Test') {
        steps {
            dir('jenkins-custom') {      // Replace 'jenkins-custom' with your actual folder
            sh 'mvn test'
            }
        }
    }

    stage('Build') {
        steps {
            dir('jenkins-custom') {
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
