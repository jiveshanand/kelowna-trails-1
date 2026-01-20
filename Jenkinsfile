pipeline {
    agent {
        docker {
            image 'node:20'
            args '-u root:root'
        }
    }
    environment {
        FIREBASE_DEPLOY_TOKEN = credentials('firebase-token-jiveshanand11')
    }
    stages {
        stage('Building') {
            steps {
                echo 'Building...'
                sh 'npm install -g firebase-tools'
            }
        }
        stage('Staging Environment') {
            steps {
                echo 'Deploying to Staging Environment...'
                sh 'firebase deploy -P kelowna-trails-production --token "$FIREBASE_DEPLOY_TOKEN"'
            }
        }
    }
}
