pipeline {
    agent any

    environment {
        VENV = "venv"
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/DineshDNS/fin-health-assess-project.git'
            }
        }

        stage('Setup Backend') {
            steps {
                dir('backend') {
                    bat 'python -m venv venv'
                    bat 'venv\\Scripts\\activate && pip install -r requirements.txt'
                }
            }
        }

        stage('Setup Frontend') {
            steps {
                dir('frontend') {
                    bat 'npm install'
                }
            }
        }

        stage('Parallel Tests') {
            parallel {

                stage('Backend Tests') {
                    steps {
                        dir('backend') {
                            bat 'venv\\Scripts\\activate && python manage.py test'
                        }
                    }
                }

                stage('Frontend Tests') {
                    steps {
                        dir('frontend') {
                            bat 'npm run test'
                        }
                    }
                }
            }
        }

        stage('Build Frontend') {
            steps {
                dir('frontend') {
                    bat 'npm run build'
                }
            }
        }

        stage('Deploy Backend') {
            steps {
                dir('backend') {
                    bat 'venv\\Scripts\\activate && python manage.py runserver'
                }
            }
        }
    }
}
