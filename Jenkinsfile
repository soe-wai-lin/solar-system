pipeline {
    agent {
        label 'Jenkins-Agent'
    }

    // agent any
    
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

        stage('Code Coverage') {
            steps {
                catchError(buildResult: 'SUCCESS', message: 'Oops! please fix next', stageResult: 'UNSTABLE') {
                    sh '''
                        npm run coverage
                        echo $?
                    '''
                }
            }
        }


        // stage('OWASP Depencies Check') {
        //     steps {
        //         dependencyCheck additionalArguments: '''--scan \'./\'
        //         --out \'./\'
        //         --format \'ALL\'
        //         --prettyPrint''', odcInstallation: 'OWASP-DepCheck-10'
        //     }
        // }
    }
    
}