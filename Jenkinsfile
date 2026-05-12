pipeline {
    agent none

    stages {

        stage('Build Application') {

            agent { label 'linux' }

            steps {

                git 'https://github.com/YOUR-USERNAME/simple-fullstack-app.git'

                sh '''
                    cd backend
                    npm install
                '''
            }
        }

        stage('Docker Build') {

            agent { label 'docker' }

            steps {

                sh '''
                    docker build -t simple-fullstack-app:v1 .
                '''
            }
        }
    }
}
