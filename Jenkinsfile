pipeline {
    agent any
    stages {
        stage('SCM') {
            steps {
                echo "Pulling source code from GitHub"
                git "https://github.com/chanat-minor/simple-nodejs-app"
            }
        }
        stage('Prerequisites') {
            parallel {
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
        stage('SonarQube analysis') {
            steps {
                script {
                            def scannerHome = '/var/jenkins_home/sonar-scanner/sonar-scanner-3.3.0.1492-linux';
                            def sonarProjectKey = 'simple-nodejs-app';
                            withSonarQubeEnv(credentialsId: 'sonarqube-local', installationName: 'SonarQube Local') {
                                // some block
                                sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=${sonarProjectKey} -Dsonar.sources=."
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
}