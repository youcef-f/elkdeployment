pipeline {

    agent any

        currentBuild.result = "SUCCESS"
        stage('Checkout'){

            checkout scm
        }
        stage('copy_elk_file') {
            sshagent (credentials: ['deploy-dev']) {
                sh 'ssh -o StrictHostKeyChecking=no -l cloudbees 192.168.10.102 uname -a'
            }
        }


}