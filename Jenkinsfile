pipeline {
    agent any
    stages {
 	stage('Test') {
	    steps {
		sh 'python3 -m venv .venv'
  		sh '.venv/bin/python -m pip install -r requirements.txt'
		sh '.venv/bin/python -m pytest -v'
	    }
        }
    }
}
