pipeline {
    agent any

    environment {
        DOCKER_PATH = "/usr/local/bin/docker"  // Caminho para o binário do Docker
    }

    stages {
        stage('Build') {
            steps {
                sh '${DOCKER_PATH} build -t project-manager .'
            }
        }

        stage('Test') {
            steps {
                script {
                    docker.image('project-manager').inside {
                        sh 'bundle exec rake test'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo "Deploying to production..."
                    // Adicione aqui seu processo de deploy
                }
            }
        }
    }
}
