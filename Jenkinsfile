pipeline {
    agent any

    environment {
	NODE_ENV = 'production'
    }

    stages {
	stage('Checkout') {
	    steps {
		git 'https://github.com/Shahrukh-Khan644/node-redis.git'
	    }
	}

	stage('Install Dependencies') {
	    steps {
		sh 'npm install'
	    }
	}

	stage('Test') {
	    steps {
		sh 'npm test'
	    }
	}

	stage('Build') {
	    steps {
		sh 'npm run build'
	    }
	}

	stage('Lint') {
	    steps {
		sh 'npm run lint'
	    }
	}

	stage('Generate Documentation') {
	    steps {
		sh 'npm run documentation'
	    }
	}

    }

    post {
	success {
	    echo 'Successfully build'
	}
	failure {
	    echo 'Build Failed'
	}
    }
}


