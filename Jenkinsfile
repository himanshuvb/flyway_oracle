pipeline {
    agent { label 'local' }

    stages {
        stage('Build & Migrate') {
            steps {
                script {
                    def tag = "rel-${env.BUILD_NUMBER}"

                    bat """
                    cd /d D:\\Oracle_flyway\\oracle-flyway

                    docker build -f docker/Dockerfile -t flyway:${tag} .

                    docker compose run --rm flyway migrate
                    """
                }
            }
        }
    }
}
