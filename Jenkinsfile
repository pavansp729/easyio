pipeline {

	agent any
	
	tools {nodejs "NodeMod"}

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