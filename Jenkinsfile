pipeline {
    agent 'any'
    stages {
        stage('docker-image-build-deploy') {
            environment {
                DOCKER_USER = credentials('DOCKER_USER_CREDENTIALS')
            }
            steps {
                sh './docker-build-publish-jenkins.sh'
            }
        }
    }
    post {
        success {
            echo 'Build ve deploy işlemleri başarıyla bitti'
        }
        failure {
            echo 'Hatalar var !'
        }
    }
}