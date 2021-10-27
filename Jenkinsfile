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
						jenkinsfile.postSuccess()
					}
				}	
			}
	}
		
	post {
			success {
				
			}				
        }
}
