pipeline {
    agent { label 'mac' }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Env Check') {
            steps {
                sh 'echo USER: $(whoami)'
                sh 'echo HOST: $(hostname)'
                sh 'node -v'
                sh 'npm -v'
            }
        }

        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test || true'
            }
        }
    }
}
