pipeline {
        agent any
        environment {
		PROJECT_ID = 'zinc-gist-283714'
 		CLUSTER_NAME = 'k8-gcloud-cluster'
 		LOCATION = 'us-west2-a'
 		CREDENTIALS_ID = 'google-key'
                    }
		
	stages {           
	     stage('Deploy to GKE') {
 			steps{
 				echo "Deployment started"
				sh 'ls -ltr'
				sh 'pwd'
				step([$class: 'KubernetesEngineBuilder', projectId: env.PROJECT_ID,
				 clusterName: env.CLUSTER_NAME, location: env.LOCATION, manifestPattern: 'deployment.yaml',
				 credentialsId: env.CREDENTIALS_ID, verifyDeployments: true])
				echo "Deployment Finished"
 	                     }
	                }
	          }
	    }
