pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                echo 'Cloning fin-health-assess-project...'
            }
        }

        stage('Frontend Stage') {
            steps {
                dir('frontend') {
                    echo 'Inside frontend folder'
                    echo 'Simulating frontend build...'
                }
            }
        }

        stage('Backend Stage') {
            steps {
                dir('backend') {
                    echo 'Inside backend folder'
                    echo 'Simulating backend setup...'
                }
            }
        }

        stage('Project Summary') {
            steps {
                echo 'Frontend + Backend pipeline executed successfully'
            }
        }
    }
}
