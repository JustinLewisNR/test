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
        stage('Post to NR') {
            steps {
                script {
                    step([$class: 'NewRelicDeploymentNotifier', notifications: [[apiKey: '4', applicationId: '', changelog: '', commit: '', deeplink: 'http://localhost:8080/job/PipelineV2/configure', deploymentType: 'BLUE_GREEN', description: '', entityGuid: 'MTE2NjAxMzJ8QVBNfEFQUExJQ0FUSU9OfDEyMDk1MjY5', groupId: '', revision: '', timestamp: '', user: 'jenkins', version: '1']]])
                }
            }
        }
    }
}

