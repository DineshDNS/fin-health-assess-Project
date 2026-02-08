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

        stage('Backend Install Requirements') {
            steps {
                dir('backend') {
                    bat 'pip install -r requirements.txt'
                }
            }
        }

        stage('Django Check') {
            steps {
                dir('backend') {
                    bat 'python manage.py check'
                }
            }
        }

        stage('Pipeline Complete') {
            steps {
                echo 'Frontend + Django backend build successful'
            }
        }
    }
}
