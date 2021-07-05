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

			withAWS(region:'ap-southeast-1') {
				s3Upload(bucket:"jenkins-build-archieve", path:'/var/jenkins_home/workspace', includePathPattern:'**/*', workingDir:'dist', excludePathPattern:'README.md,**/node_modules')
			}

        }
}
