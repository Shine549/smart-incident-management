pipeline {

    agent any

    environment {
        GIT_REPO = 'https://github.com/Shine549/smart-incident-management.git'
        GIT_BRANCH = 'main'

        DOCKER_USERNAME = 'shinedas'
        DOCKER_BACKEND_IMAGE = 'shinedas/smart-incident-management-frontend'       
        DOCKER_FRONTEND_IMAGE = 'shinedas/smart-incident-management-backend'

        SONARQUBE_SERVER = 'SonarQube'
    }

    options {
        timestamps()
        disableConcurrentBuilds()
    }

    stages {

        stage('1. Code Checkout') {
            steps {
                echo '=========================================='
                echo 'Checking out source code from GitHub'
                echo '=========================================='

                git branch: "${GIT_BRANCH}",
                    url: "${GIT_REPO}"

                echo 'Repository cloned successfully.'
            }
        }

        stage('2. Build Backend (Demo)') {
            steps {
                echo '------------------------------------------'
                echo 'DEMO STAGE'
                echo 'Normally Maven would compile the backend.'
                echo 'Example: mvn clean package'
                echo 'Skipped because source code is unavailable.'
                echo '------------------------------------------'
            }
        }

        stage('3. Build Frontend (Demo)') {
            steps {
                echo '------------------------------------------'
                echo 'DEMO STAGE'
                echo 'Normally npm install and npm run build execute here.'
                echo 'Skipped because package.json/source is unavailable.'
                echo '------------------------------------------'
            }
        }

        stage('4. Unit Tests (Demo)') {
            steps {
                echo '------------------------------------------'
                echo 'DEMO STAGE'
                echo 'Normally JUnit / React tests execute here.'
                echo 'All tests assumed PASS for demo.'
                echo '------------------------------------------'
            }
        }

        stage('5. SonarQube Analysis (Demo)') {
            steps {
                echo '------------------------------------------'
                echo 'DEMO STAGE'
                echo 'Normally SonarScanner would run here.'
                echo 'Skipped because project source is unavailable.'
                echo '------------------------------------------'
            }
        }

        stage('6. Quality Gate (Demo)') {
            steps {
                echo '------------------------------------------'
                echo 'DEMO STAGE'
                echo 'Quality Gate PASSED (Demo)'
                echo '------------------------------------------'
            }
        }

        stage('7. Docker Build (Demo)') {
            steps {
                echo '------------------------------------------'
                echo 'DEMO STAGE'
                echo 'Normally Docker images would be built.'
                echo "docker build -t ${DOCKER_BACKEND_IMAGE}:latest backend/"
                echo "docker build -t ${DOCKER_FRONTEND_IMAGE}:latest frontend/"
                echo 'Skipped for demo.'
                echo '------------------------------------------'
            }
        }

        stage('8. Docker Tag (Demo)') {
            steps {
                echo '------------------------------------------'
                echo 'DEMO STAGE'
                echo 'Images would be tagged here.'
                echo "${DOCKER_BACKEND_IMAGE}:latest"
                echo "${DOCKER_FRONTEND_IMAGE}:latest"
                echo '------------------------------------------'
            }
        }

        stage('9. Docker Push (Demo)') {
            steps {
                echo '------------------------------------------'
                echo 'DEMO STAGE'
                echo 'Normally Jenkins logs into Docker Hub'
                echo 'using dockerhub-creds and pushes images.'
                echo 'Skipped.'
                echo '------------------------------------------'
            }
        }

        stage('10. Deploy to Kubernetes (Demo)') {
            steps {
                echo '------------------------------------------'
                echo 'DEMO STAGE'
                echo 'Normally these commands execute:'
                echo 'kubectl apply -f k8s/'
                echo 'Deployment skipped for demo.'
                echo '------------------------------------------'
            }
        }

        stage('11. Verify Deployment (Demo)') {
            steps {
                echo '------------------------------------------'
                echo 'DEMO STAGE'
                echo 'Normally verification commands run:'
                echo 'kubectl get pods'
                echo 'kubectl get svc'
                echo 'kubectl rollout status deployment/backend'
                echo 'Verification skipped.'
                echo '------------------------------------------'
            }
        }

        stage('12. Build Notification') {
            steps {
                echo '=========================================='
                echo 'Pipeline completed successfully.'
                echo 'Notification would normally be sent here.'
                echo '=========================================='
            }
        }
    }

    post {

        always {
            echo 'Cleaning Jenkins Workspace'
            cleanWs()
        }

        success {
            echo 'BUILD STATUS : SUCCESS'
        }

        failure {
            echo 'BUILD STATUS : FAILURE'
        }
    }
}
