pipeline {
    options {
	buildDiscarder(logRotator(numToKeepStr: '1', artifactNumToKeepStr: '1'))
    }
    agent any
    parameters {
	booleanParam(name: 'Produce_deb', defaultValue: false, description: 'Should we produce the deb package') 
    }
    stages {
	stage ('Build Deb') {
	    when {
		expression { params.Produce_deb == true }
	    }

	    agent {
		docker {
		    image 'alpine:latest'
		}
	    }

	    environment {
		DEBVAR = 'yep'
	    }

	    steps {
		sh 'echo ${DEBVAR}'
		sh 'pwd'
	    }
	}

	stage ('Build NonDeb') {
	    when {
		expression { params.Produce_deb == false }
	    }

	    environment {
		DEBVAR = 'nop'
	    }

	    steps {
		sh 'echo ${DEBVAR}'
	    }
	}
    }
}
