pipeline {
    agent {
        docker {
            image 'python:3.11-slim'
            args '--user root'
        }
    }

    stages {
        stage('Syntax Check') {
            steps {
                sh 'python -m py_compile main.py'
            }
        }
        stage('Test') {
            steps {
                sh 'pip install --no-cache-dir -r requirements.txt'
                sh 'pytest -v'
            }
        }
    }

    post {
        failure {
            echo 'BUILD FEHLGESCHLAGEN: Python-Syntaxfehler in main.py.'
        }
        success {
            echo 'Build erfolgreich.'
        }
    }
}
