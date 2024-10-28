pipeline {
    agent {
        docker { image 'node:lts' }  // Use Node.js Docker image as the build agent
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/AinPhoenix/my-sample-app-jenkins.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }

        stage('Deploy to Staging') {
            when {
                branch 'main'
            }
            steps {
                echo 'Deploying to staging environment...'
                // Placeholder for deployment commands
            }
        }
    }

    post {
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
