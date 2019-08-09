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

                echo 'scp through 192.168.10.102'
                withCredentials([file(credentialsId: 'elklocalvm2', variable: 'varelklocalvm')]) {
                    //bat 'ssh -o StrictHostKeyChecking=no root@192.168.10.102  -i %varelklocalvm%  uname -a'
                    bat 'scp -pr -i  %varelklocalvm%  -o StrictHostKeyChecking=no  .\\fms\\elk_server\\logstash    root@192.168.10.102:/tmp/'
                }
            }
        }
        stage('configLogstash') {
            steps{

                echo 'ssh through 192.168.10.102'
                withCredentials([file(credentialsId: 'elklocalvm2', variable: 'varelklocalvm')]) {
                    bat 'ssh -o StrictHostKeyChecking=no root@192.168.10.102  -i %varelklocalvm%  cp -r /tmp/logstash/*  /etc/logstash/conf.d/'
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