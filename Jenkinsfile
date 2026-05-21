pipeline {
    agent any

    stages {
        stage('Syntax Check') {
            steps {
                sh 'python -m py_compile main.py'
            }
        }
        stage('Test') {
            steps {
                sh 'pip install --no-cache-dir -r requirements.txt'
                sh 'python -m pytest -v'
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
