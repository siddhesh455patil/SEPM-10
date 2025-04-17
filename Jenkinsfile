pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/name/myfirst.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                dir('DockerJenkinsExperiment') {
                    // Use Windows CMD commands
                    bat 'dir'  // Check that Dockerfile is visible
                    bat 'docker build -t my-docker-webapp .'
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker run -d -p 8081:80 my-docker-webapp'
            }
        }
    }
}
