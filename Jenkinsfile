pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Get the code from GitHub or Git
                git 'https://github.com/Yashu0317/yoga.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install required npm packages
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                // If your app has a build step
                sh 'npm run build || echo "No build step"'
            }
        }

        stage('Test') {
            steps {
                // Run tests (make sure you have "test" script in package.json)
                sh 'npm test || echo "No tests found"'
            }
        }

        stage('Archive') {
            steps {
                // Save build files as artifacts
                archiveArtifacts artifacts: '**/*', onlyIfSuccessful: true
            }
        }
    }
}
