pipeline {
    agent {
        label 'Jenkins-Agent'
    }
    tools {
        nodejs 'nodejs-22.6.0'  
    }

    stages {
        stage('VM Node Version') {
            steps {
                sh '''
                    npm -v
                    node -v
                '''
            }
        }
    }
}