@Library('jenkinsScript@main') _
pipeline {

	agent {
		label 'ecs'
	}
	
	tools {nodejs "NodeMod"}

    	stages {
		stage('Build') {
			steps {
				script {
					jenkinsfile.buildApp()
					postAction.postSuccess()
				}
			}
		}
	}
		
	post {
		success {
			sh 'echo "Reached Post Action" '
		}				
        }
}
