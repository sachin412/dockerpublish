node {
	def app

	stage('Clone repository') {
		checkout scm
	}

	stage('Build image') {
		app = docker.build('sachin41/myubuntuapache')
	}

	stage('Test') {
		app.inside {
			sh 'apt install gnupg2 pass -y'
		}
	}

	stage('Push image') {
		docker.withRegistry('', 'docker-hub') {
			app.push("${env.BRANCH_NAME}-latest")
			app.push("${env.BRANCH_NAME}-${env.BUILD_NUMBER}")
		}
	}
}
