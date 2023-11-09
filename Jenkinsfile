pipeline {
    agent any
    tools {
        nodejs 'node16'
        go 'go1.17'
    }
    environment {
        CUSTOM_WORKSPACE = "/tmp/jenkins_workspace"
    }
    stages {
        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }
        stage('Checkout from Git') {
            steps {
                dir(CUSTOM_WORKSPACE) {
                    git branch: 'main', url: 'https://github.com/Amey3556/devops-fullstack-app.git'
                }
            }
        }
        stage('Install Dependencies') {
            steps {
                dir(CUSTOM_WORKSPACE) { 
                    sh "npm install"
                }
            }
        }
        stage('Deploy to Container') {
            steps {
                dir(CUSTOM_WORKSPACE) {
                    sh 'docker-compose -f docker-compose.yml up -d'
                }
            }
        }
    }
}
