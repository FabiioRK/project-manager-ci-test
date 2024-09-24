pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    docker.build('my-rails-app')
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    docker.image('my-rails-app').inside {
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
