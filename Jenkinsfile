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
                    bat '''
                           ssh -o StrictHostKeyChecking=no -l root 192.168.10.102 uname -a
                    '''

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