pipeline {

	agent any
	
	tools {nodejs "NodeJs"}

	stages {

		stage('Build') {
			steps {
				sh 'npm install'
			}
		}

    }

	post {

		cleanup{
             deleteDir()
        }

	}

}
