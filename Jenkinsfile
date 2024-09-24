pipeline {
    agent any

    environment {
        PATH = "/usr/local/bin:/bin:/usr/bin:/usr/local/bin/docker"
    }

    stages {
        stage('Build') {
            steps {
                sh 'docker --version'
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
