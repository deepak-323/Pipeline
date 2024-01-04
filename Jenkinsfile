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
	stage('Install dependencies') {
            steps {
                // Install Python dependencies
                sh 'pip install -r requirements.txt'
            }
        }
	stage('Run Python Script') {
            steps {
                script { // Your build commands go here 
	          sh "chmod +x -R ${env.WORKSPACE}"
		  sh 'python TF_Inference_cifar.py'
	       }
            }
        }
    }
}
