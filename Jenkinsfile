pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/AnkithreddyBureddy/Portfolio_Website.git'
        BRANCH = 'main'  // Change to your branch name if it's different
    }

    stages {
        // Stage 1: Checkout the code from GitHub
        stage('Checkout') {
            steps {
                script {
                    echo 'Checking out the code from GitHub repository...'
                    // Pulling the code from the specified GitHub repository and branch
                    git branch: BRANCH, url: REPO_URL
                }
            }
        }

        // Stage 2: List Files (Debugging stage)
        stage('List Files') {
            steps {
                script {
                    echo 'Listing files in the workspace...'
                    // You can list files to debug if the checkout was successful
                    sh 'ls -la'  // On Linux/Unix systems or use 'dir' for Windows
                }
            }
        }

        // Stage 3: Setup (Dependencies or preparation step)
        stage('Setup') {
            steps {
                script {
                    echo 'Setting up environment for website build...'
                    // Any additional setup or preparation tasks can be added here
                    // e.g., installing dependencies for the site (e.g., using npm, yarn, etc. for static assets)
                }
            }
        }

        // Stage 4: Build (Simulated build for a static website)
        stage('Build') {
            steps {
                script {
                    echo 'Building the static website...'
                    // For a static website, you could minify CSS, bundle JS, or other tasks
                    // This can also include compressing assets or other build-related tasks
                }
            }
        }

        // Stage 5: Test (Basic test stage)
        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                    // Here we check if certain files exist as a basic test for the static site
                    def file = 'index.html'
                    if (!fileExists(file)) {
                        error "Test failed: ${file} not found!"
                    } else {
                        echo "${file} exists!"
                    }
                }
            }
        }

        // Stage 6: Deploy (Optional, if deploying to any hosting platform)
        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying the website...'
                    // You can add steps to deploy to GitHub Pages, AWS, GCP, or any hosting service
                    // Example: Using GitHub Pages or another cloud provider for static hosting
                }
            }
        }

        // Stage 7: Notify (Send email notification)
        stage('Notify') {
            steps {
                script {
                    echo 'Sending email notification...'
                    // Notifying team or user about the build status (success or failure)
                    mail to: 'your.email@example.com',
                         subject: "Jenkins Build Notification",
                         body: "The Jenkins build has completed. Check Jenkins for details."
                }
            }
        }
    }

    // Post-build actions (notifications)
    post {
        success {
            echo "Build was successful!"
        }
        failure {
            echo "Build failed!"
        }
    }
}
