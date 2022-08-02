pipeline {
    agent any
    
    environment {
        asdf = 'QWER'
	awesomeVersion = sh(returnStdout: true, script: 'echo 0.0.1')

    }

    stages {
        stage('Env Variables') {
            steps {
                sh "printenv"
            }
        }
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Test') {
            steps {
                build 'test'
            }
        }
    }
}

