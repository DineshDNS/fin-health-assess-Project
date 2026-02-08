pipeline {
    agent any

    stages {

        stage('Frontend Install') {
            steps {
                dir('frontend') {
                    bat 'npm install'
                }
            }
        }

        stage('Frontend Build') {
            steps {
                dir('frontend') {
                    bat 'npm run build'
                }
            }
        }

        stage('Create Virtual Env') {
            steps {
                dir('backend') {
                    bat 'python -m venv venv'
                }
            }
        }

        stage('Install Backend Requirements') {
            steps {
                dir('backend') {
                    bat 'venv\\Scripts\\pip install -r requirements.txt'
                }
            }
        }

        stage('Django Check') {
            steps {
                dir('backend') {
                    bat 'venv\\Scripts\\python manage.py check'
                }
            }
        }

        stage('Pipeline Complete') {
            steps {
                echo 'Frontend + Django (venv) build successful'
            }
        }
    }
}
