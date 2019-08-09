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
                //sshagent (credentials: ['0e8f2f17-bf5d-4585-9740-41ac29c689e9']) {
                  //  sh 'ssh -o StrictHostKeyChecking=no -l root 192.168.10.102 uname -a'
                //}

                withCredentials([file(credentialsId: 'elklocalvm2', variable: 'varelklocalvm')]) {
                    bat 'ssh -o StrictHostKeyChecking=no root@192.168.10.102  -i %varelklocalvm%  uname -a'
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