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
		stage('S3 Upload') {

			dir('/home/jenkins/workspace/ecs-demo'){
				pwd(); //Log current directory
 
				withAWS(region:'ap-aoutheast-1') {
					// Upload files from working directory 'dist' in your project workspace
					s3Upload(bucket:"jenkins-build-archieve", workingDir:'dist', includePathPattern:'**/*');
				}
			};
		}

		cleanup{
             deleteDir()
        }

	}

}
