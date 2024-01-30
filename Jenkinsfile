pipeline {
    agent {
        node {
            label 'docker-agent-python'
        }
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/RaupeCHR/Jenkins-DockerHA.git'
            }
        }
        stage('Build') {
            steps {
                sh 'pip install -r myapp/requirements.txt'
            }
        }
        stage('Test') {
            steps {
                sh 'python3 myapp/tests.py'
            }
        }
        stage('Run') {
            steps {
                sh 'python3 myapp/main.py'
            }
        }
    }
}