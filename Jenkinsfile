pipeline {
    agent any

    stages {

        stage('Parallel Build') {
            parallel {

                stage('Frontend Pipeline') {
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
                    }
                }

                stage('Backend Pipeline') {
                    stages {

                        stage('Install Requirements') {
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
                    }
                }

            }
        }

        stage('Finish') {
            steps {
                echo 'Parallel build completed successfully'
            }
        }
    }
}
