pipeline {
    agent {
        docker {
            image 'node:14.15.1'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages {
        stage('Build Docker Image') {
            steps {
                sh '''
                    echo "FROM nginx:alpine" > Dockerfile
                    echo "COPY index.html /usr/share/nginx/html" >> Dockerfile
                '''
                sh 'docker build -t mynginximage .'
            }
        }
    }
}
