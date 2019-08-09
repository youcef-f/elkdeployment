pipeline {

    agent any

    stages {

        stage('Checkout') {
            checkout scm
        }
        stage('copy_elk_file') {
            sshagent(credentials: ['elklocalvm']) {
                echo 'ssh through 192.168.10.102'
                sh 'ssh -o StrictHostKeyChecking=no -l root 192.168.10.102 uname -a'
            }
        }
        steps('deleteWorkspace') {
            echo 'Deploying....'
            deleteDir() /* clean up our workspace */
        }


    }
}