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
		always(region:'ap-southeast-1') {
			s3Upload(bucket:"jenkins-build-archieve/${JOB_NAME}-${BUILD_NUMBER}", sourceFile:'**/*', storageClass: 'STANDARD', selectedRegion: 'hudson.plugins.s3.ap-southeast-1', uploadFromSlave: True)
		}
        }
}
