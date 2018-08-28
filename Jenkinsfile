pipeline {
    agent any
    parameters {
	booleanParam(name: 'Produce_deb', defaultValue: false, description: '') 
    }
    stages {
	stage ('Build Deb') {

	    environment {
		DEBVAR = 'yep'
	    }

	    steps {
		sh 'echo ${DEBVAR}'
	    }
	}

	stage ('Build NonDeb') {

	    environment {
		DEBVAR = 'nop'
	    }

	    steps {
		sh 'echo ${DEBVAR}'
	    }
	}
    }
}
