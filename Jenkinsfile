pipeline {
    agent any
    
    environment {
        entityGuid = 'MTE2Nj*****************************'
    }

    stages {
        stage('Check env') {
            steps {
                sh "printenv"
            }
        }
        stage('Post to NR') {
            steps {
                script {
                    step([$class: 'NewRelicDeploymentNotifier', 
                    notifications: [[
                        apiKey: '4', 
                        applicationId: '', 
                        changelog: '', 
                        commit: '', 
                        deeplink: 'http://localhost:8080/job/PipelineV2/configure', 
                        deploymentType: 'BLUE_GREEN', description: '', 
                        entityGuid: "${entityGuid}", groupId: '', revision: '', timestamp: '', user: 'jenkins', version: '1']
                        ]])
                }
            }
        }
    }
}

