pipeline {
    agent any
    stages {
        stage('SCM') {
            steps {
                echo "Pulling source code from GitHub"
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
                        echo "Check vulnerability in dependencies used by the application"
                    }
                }
                stage('Credential Scan') {
                    steps {
                        echo "Scan for credential in source code"
                    }
                }
            }
        }
        stage('Build') {
            steps {
                echo "Building application image"
            }
        }
        stage('Vulnerability Scan') {
            steps {
                echo "Scan for vulnerability in image"
            }
        }
        stage('Deploy to Dev') {
            steps {
                echo "Deploy to devepment environment"
            }
        }
        stage('Integration Test') {
            steps {
                echo "Perform application integration test"
            }
        }
        stage('Deploy to UAT') {
            steps {
                echo "Deploy to UAT environment"
            }
        }
        stage('Functional Test') {
            steps {
                echo "Perform functional test or whatever test that is neccessary"
            }
        }
        stage('Perf Test') {
            steps {
                echo "Perform performance test"
            }
        }
        stage('Push Image') {
            steps {
                echo "Push application image in a container registry on cloud e.g. ECR, GCR"
            }
        }
        stage('Deploy to prod') {
            steps {
                echo "Deploy to production environment using Blue-Green or Canary Deployment, roll back if fail"
            }
        }
        stage('PIR') {
            steps {
                echo "(Optional) Perform Post Implementation Test, roll back if fails"
            }
        }
    }
})