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
		always(region: 'ap-southeast-1') {
			s3Upload(profileName: 's3-build-storage', entries: [bucket: 'jenkins-build-archieve', sourceFile: '**/*', storageClass: 'STANDARD', selectedRegion: 'hudson.plugins.s3.ap-southeast-1', uploadFromSlave: True ], consoleLogLevel: True, userMetadata: ['name': 'ecs-demo'], dontWaitForConcurrentBuildCompletion: False, dontSetBuildResultOnFailure: True)
		}
        }
}
