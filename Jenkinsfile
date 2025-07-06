pipeline {
    agent {
        // label 'Jenkins-Agent'
        any
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
    
    
        stage('NPM dependiencies audit') {
            steps {
                sh '''
                    npm audit --audit-level=critical
                    echo $?
                '''
            }
        }

        stage('OWASP Depencies Check') {
            steps {
                dependencyCheck additionalArguments: '''--scan \'./\'
                --out \'./\'
                --format \'ALL\'
                --prettyPrint''', odcInstallation: 'OWASP-DepCheck-10'
            }
        }
    }
    
}