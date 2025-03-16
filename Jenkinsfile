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
                    git url: REPO_URL, branch: BRANCH
                }
            }
        }

        // Stage 2: Build (Simulated step for a static HTML website)
        stage('Build') {
            steps {
                script {
                    echo 'Building the website...'
                    // For a static HTML website, you could minify CSS, JavaScript, or add other build tasks here
                    // Example placeholder for building the project
                }
            }
        }

        // Stage 3: Test (Basic test step)
        stage('Test') {
            steps {
                script {
                    echo 'Running basic tests...'
                    // For example, checking if the 'index.html' file exists
                    def file = 'index.html'
                    if (!fileExists(file)) {
                        error "Test failed: ${file} not found!"
                    } else {
                        echo "${file} exists!"
                    }
                }
            }
        }

        // Stage 4: Deploy (Optional step for deployment)
        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying the website...'
                    // You can deploy the website to any hosting platform, such as GitHub Pages, AWS, or GCP
                    // Example placeholder for deployment, add your deployment steps here
                }
            }
        }
    }

    // Post-build actions (notifications)
    post {
        success {
            mail to: 'your.email@example.com',
                 subject: "Build Successful: ${env.JOB_NAME}",
                 body: "The build was successful. Check the Jenkins job for details."
        }
        failure {
            mail to: 'your.email@example.com',
                 subject: "Build Failed: ${env.JOB_NAME}",
                 body: "The build failed. Please check Jenkins for the details."
        }
    }
}
