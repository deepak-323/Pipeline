pipeline {
    agent any
    stages {
        stage('Git Checkout') {
            steps {
                script {
                    git branch: 'main',
                        credentialsId: 'Credential ID',
                        url: 'https://github.com/deepak-323/Pipeline.git'
                }
            }
        }
	 stage('Build') {
            steps {
               script { // Your build commands go here
                 sh 'TF_Inference_cifar.py'
	       }
            }
        }
    }
}

