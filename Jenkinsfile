pipeline {
    agent any

    environment {
        NODE_ENV = 'development'
    }
 HEAD

    tools {
        nodejs 'NodeJS-22.12.0' // Make sure this is configured in Jenkins
    }

    stages {
        stage('Clone repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Devopscohort1/tunesky-repo.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm run test'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
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

    tools {
        nodejs 'NodeJs 21.2.0'
    }
    stages{
        stage('clone repository') {
            steps {
                git branch: 'main', url: 'http '
            }
        }
    }
}
 42c3cfd (Fix: Use working pip path for requirements installation)
