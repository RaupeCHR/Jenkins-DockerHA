pipeline {
    agent {
        node {
            label 'docker-agent-python'
        }
    }
    environment {
        APP_REQUIREMENTS = 'myapp/requirements.txt'
        APP_TESTS = 'myapp/tests.py'
        APP_MAIN = 'myapp/main.py'
        GIT_BRANCH = 'main' // Hier kannst du den Branch-Namen ändern
    }
    stages {
        stage('Checkout') {
            steps {
                script {
                    git branch: "${env.GIT_BRANCH}", url: 'https://github.com/RaupeCHR/Jenkins-DockerHA.git'
                }
            }
        }
        stage('Build') {
            steps {
                script {
                    sh "pip install -r ${env.APP_REQUIREMENTS}"
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh "python3 ${env.APP_TESTS}"
                }
            }
        }
        stage('Run') {
            steps {
                script {
                    sh "python3 ${env.APP_MAIN}"
                }
            }
        }
    }
}