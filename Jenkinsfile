pipeline {

	agent any

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
