pipeline {
    agent any
    stages {
        stage('SCM') {
            steps {
                git "https://github.com/sindresorhus/open"
            }
        }
        stage('Prerequisites') {
            parallel {
                stage('SonarQube analysis') {
                    steps {
                        withSonarQubeEnv("SonarQube local") { // If you have configured more than one global server connection, you can specify its name
                        }
                    }
                }
                stage('Dependency check') {
                    steps {
                        echo "Hello world"
                    }
                }
                stage('Credential Scan') {
                    steps {
                        echo "Hello world"
                    }
                }
                stage('Vulnerability Scan') {
                    steps {
                        echo "Hello world"
                    }
                }
            }
        }
        stage('Build') {
            steps {
                echo "Hello world"
            }
        }
        stage('Deploy to Dev') {
            steps {
                echo "Hello world"
            }
        }
        stage('Integration Test') {
            steps {
                echo "Hello world"
            }
        }
        stage('Deploy to UAT') {
            steps {
                echo "Hello world"
            }
        }
        stage('Functional Test') {
            steps {
                echo "Hello world"
            }
        }
        stage('Perf Test') {
            steps {
                echo "Hello world"
            }
        }
        stage('Deploy to prod') {
            steps {
                echo "Hello world"
            }
        }
        stage('PIR') {
            steps {
                echo "Hello world"
            }
        }
    }
}