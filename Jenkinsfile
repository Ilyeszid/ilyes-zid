pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {

        stage('Checkout') {
            steps {
                script {
                    def repoUrl = 'https://github.com/Ilyeszid/ilyes-zid.git'

                    git branch: 'main',
                        url: repoUrl
                }
            }
        }

        stage('Build Maven') {
            steps {
                echo 'Starting Maven Build...'
                sh 'mvn clean package'
            }
        }

    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}
