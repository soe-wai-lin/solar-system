pipeline {
    agent {
        label 'Jenkins-Agent'
    }
    tools {
        nodejs 'nodejs-22.6.0'  
    }

    stages {
        stage('Install dependencies') {
            steps {
                sh 'npm install --no-audit'
            }
        }
    }
}