pipeline {

    agent any



    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('copy_elk_file') {
            steps{

                echo 'ssh through 192.168.10.102'

                // '0e8f2f17-bf5d-4585-9740-41ac29c689e9
                sshagent (credentials: ['elklocalvm']) {
                    sh 'ssh -o StrictHostKeyChecking=no -l root 192.168.10.102 uname -a'
                }
            }

        }

        /*
        stage('deleteWorkspace') {
            steps {
                echo 'Deploying....'
                deleteDir() // clean up our workspace
            }

        }
        */



    }
}