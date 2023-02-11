pipeline {
    agent {
        docker {
            image 'maven:3.6.3-jdk-8'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages {
        stage('Build Maven Project') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myimage .'
            }
        }
    }
}
