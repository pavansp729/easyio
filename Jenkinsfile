pipeline {

	agent {
		label 'ecs'
	}
	
	tools {nodejs "NodeMod"}

	stages {

		stage('Build') {
			steps {
				sh 'npm install'
			}
		}

    }

	post {
		stage('Upload') {

			dir('/home/jenkins/workspace/ecs-demo'){
				pwd(); //Log current directory
 
				withAWS(region:'ap-southeast-1') {
					// Upload files from working directory 'dist' in your project workspace
					s3Upload(bucket:"jenkins-build-archieve", workingDir:'ecs-demo', includePathPattern:'**/*', path:'ecs-demo');
				}
			};
		}

		cleanup{
             deleteDir()
        }

	}

}
