pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/AnkithreddyBureddy/Portfolio_Website.git'
        BRANCH = 'main'  // Change to your branch name if it's different
    }

    stages {
    stage('Checkout') {
            steps {
                script {
                    echo 'Checking out the code from GitHub repository...'
                    // Pulling the code from the specified GitHub repository and branch
                    git branch: BRANCH, url: REPO_URL
                }
            }
        }

    stage('List Files') {
            steps {
                script {
                    echo 'Listing files in the workspace...'
                    sh 'ls -la'  // If you're on a Unix-based system, use 'ls -la'
                    // For Windows, you can use: 'dir'
                }
            }
        }

    stage('Setup') {
            steps {
                script {
                    echo 'Setting up environment for website build...'
                    // Placeholder for any additional setup if needed
                }
            }
        }

    stage('Build') {
            steps {
                script {
                    echo 'Building the static website...'
                    // Example build command, replace with actual build commands
                }
            }
        }

    stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                    // Basic test for the static website
                    def file = 'index.html'
                    if (!fileExists(file)) {
                        error "Test failed: ${file} not found!"
                    } else {
                        echo "${file} exists!"
                    }
                }
            }
        }

    stage('Deploy') {
            steps {
                script {
                    echo 'Deploying the website...'
                    // Placeholder for deployment steps if needed
                }
            }
        }

    stage('Notify') {
            steps {
                script {
                    echo 'Sending email notification...'
                    mail to: 'your.email@example.com',
                         subject: "Jenkins Build Notification",
                         body: "The Jenkins build has completed. Check Jenkins for details."
                }
            }
        }
    }

    post {
        success {
            echo "Build was successful!"
        }
        failure {
            echo "Build failed!"
        }
    }
}
