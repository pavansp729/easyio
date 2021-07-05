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
			s3Upload(bucket:"jenkins-build-archieve", sourceFile:'**/*', storageClass: 'STANDARD', selectedRegion: 'ap-southeast-1', uploadFromSlave: True)
		}
        }
}
