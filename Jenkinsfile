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
			success {
				s3Upload consoleLogLevel: 'INFO', dontSetBuildResultOnFailure: false, dontWaitForConcurrentBuildCompletion: true, entries: [[bucket: 'jenkins-build-archieve/${JOB_NAME}-${BUILD_NUMBER}', excludedFile: '**/node_modules/**', flatten: false, gzipFiles: false, keepForever: false, managedArtifacts: false, noUploadOnFailure: false, selectedRegion: 'ap-southeast-1', showDirectlyInBrowser: false, sourceFile: '**/*', storageClass: 'STANDARD', uploadFromSlave: true, useServerSideEncryption: false]], pluginFailureResultConstraint: 'FAILURE', profileName: 's3-build-storage', userMetadata: [[ key: 'git_branch', value: "${env.BRANCH_NAME}"], [ key: 'build_number', value: "${env.BUILD_NUMBER}"]]	
			}				
        }
}
