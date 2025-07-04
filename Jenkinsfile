pipeline {
    agent {
        label 'Jenkins-Agent'
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