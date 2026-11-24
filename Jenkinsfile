pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Python Requirements') {
            steps {
                sh '''
                    python3 -m venv .venv
                    . .venv/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                    . .venv/bin/activate
                    pytest
                '''
            }
        }

        stage('SonarQube Analysis') {
            steps {
                script {
                    def scannerHome = tool 'SonarScanner'
                    withSonarQubeEnv(
			installationName: 'SonarQube',
			credentialsId: 'sonar-analysis-token'
		    ) {
                        sh """
                            ${scannerHome}/bin/sonar-scanner \
                            -Dsonar.projectKey=aceest-fitness-assignment-2 \
                            -Dsonar.projectName='ACEest Fitness Assignment 2' \
                            -Dsonar.sources=app.py \
                            -Dsonar.tests=tests \
                            -Dsonar.test.inclusions=tests/**/*.py \
                            -Dsonar.python.version=3.9 \
                            -Dsonar.exclusions=.venv/**,**/__pycache__/**
                        """
                    }
                }
            }
        }
    }
}

