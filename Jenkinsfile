pipeline {
    agent any
    parameters {
	booleanParam(name: 'Produce_deb', defaultValue: false, description: 'Should we produce the deb package') 
    }
    stages {
	stage ('Build Deb') {
	    when {
		expression { params.Produce_deb == true }
	    }

	    environment {
		DEBVAR = 'yep'
	    }

	    steps {
		sh 'echo ${DEBVAR}'
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
