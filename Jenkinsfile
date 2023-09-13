pipeline {
    agent {
        node {
            label 'slavenode'
        }
    }
    stages {
        stage('Checkout') {
            steps {
               git branch: 'main', url: 'https://github.com/Chandandhani/nihar.git'
            }
        }

        stage('docker Build') {
            steps {
               sh 'docker build -t myimage:${BUILD_NUMBER}  .'
            }
        }

        stage('Test') {
            steps {
                sh 'docker run -itd --name my-container -p 80:80  myimage:${BUILD_NUMBER}'
            }
        }

       
    }

    
}
