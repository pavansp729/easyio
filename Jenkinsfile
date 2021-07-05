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
				s3Upload(file:'/var/jenkins_home/workspace', bucket:'jenkins-build-archieve', path:'build/')
			}

        }
}
