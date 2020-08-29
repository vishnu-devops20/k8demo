pipeline {
        agent any
        environment {
		 registry = "vishnu-devops20/sprint6demo"
                 registryCredential = 'docker-cred'
                 dockerImage = ''
		PROJECT_ID = 'wired-rex-283811'
 		CLUSTER_NAME = 'sprint6-demo-gcloud-cluster2'
 		LOCATION = 'us-east1-b'
 		CREDENTIALS_ID = 'google-key'
                    }
		
	stages {           
	     stage('Deploy to GKE') {
 			steps{
 				echo "Deployment started"
				sh 'ls -ltr'
				sh 'pwd'
				step([$class: 'KubernetesEngineBuilder', projectId: env.PROJECT_ID,
				 clusterName: env.CLUSTER_NAME, location: env.LOCATION, manifestPattern: 'sample.yaml',
				 credentialsId: env.CREDENTIALS_ID, verifyDeployments: true])
				echo "Deployment Finished"
 	                     }
	                }
	          }
	    }
