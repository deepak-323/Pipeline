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
	stage('Test') {
            steps {
                script { // Your build commands go here 
	          sh "chmod +x -R ${env.WORKSPACE}" 
		  sh '/usr/bin/python3 /var/lib/jenkins/workspace/pipeline-1/TF_Inference_cifar.py'
	       }
            }
        }
       stage('Publish') {
           steps {
	     archiveArtifacts artifacts: '/var/lib/jenkins/jobs/pipeline-1/builds/'
	   }
       }
    }
}
