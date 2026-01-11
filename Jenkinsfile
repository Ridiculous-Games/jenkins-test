pipeline {
    agent any

    stages {
        stage('Check Credential Config') {
            steps {
                bat 'git config --list | findstr credential'
                bat 'type C:\\Users\\Eric\\.git-credentials'
            }
        }

        stage('Test Credential Fill') {
            steps {
                bat '''
                    echo protocol=https > %TEMP%\\credtest.txt
                    echo host=github.com >> %TEMP%\\credtest.txt
                    echo. >> %TEMP%\\credtest.txt
                    type %TEMP%\\credtest.txt | git credential fill
                '''
            }
        }

        stage('Test Git Access') {
            steps {
                bat 'git ls-remote https://github.com/Ridiculous-Games/jenkins-test.git HEAD'
            }
        }
    }
}
