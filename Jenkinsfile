pipeline {
    agent any

    stages {
        stage('Check Credential Config') {
            steps {
                bat 'git config --list | findstr credential'
                bat 'type C:\\Users\\Eric\\.git-credentials'
            }
        }

        stage('Test Git Access') {
            steps {
                bat 'git ls-remote https://github.com/Ridiculous-Games/jenkins-test.git HEAD'
            }
        }

        stage('Test Bitbucket Access') {
            steps {
                bat 'git ls-remote https://bitbucket.org/djlittlerabbit/rgcommon.git HEAD'
            }
        }
    }
}
