pipeline {
    agent any
    stages {
 	stage('Test') {
	    steps {
		sh 'pyhton3 -m venv .venv'
  		sh '.venv/bin/python -m pip install -r requirements.txt'
		sh '.venv/bin/pythin -m pytest -v'
	    }
        }
    }
}
