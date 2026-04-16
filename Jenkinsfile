pipeline {
    agent { label 'window' }

    environment {
        TAG = "rel-${env.BUILD_NUMBER}"
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Image') {
            steps {
                bat """
                docker build -f docker/Dockerfile -t flyway:%TAG% .
                """
            }
        }

        stage('Flyway Migration') {
            steps {
                bat """
                set TAG=%TAG%
                docker-compose run --rm flyway migrate
                """
            }
        }
    }
}
