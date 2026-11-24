stage('SonarQube Analysis') {
    steps {
	script {
	    def scannerHome = tool 'SonarScanner'
	    withSonarQubeEnv('SonarQube') {
		sh "S[scannerHome}/bin/sonar-scanner -Dsonar.projectKey=aceest-fitness-assignment-2 -Dsonar.projectName='ACEest Fitness Assignment 2' =Dsonar.sources=app.py -Dsonar.test.inclusions=tests/**/*.py -Dsonar.python.version=3.9 -Dsonar.exclusions=.venv/**,**/_pycache_/**"
	    }
	}
    }
}
