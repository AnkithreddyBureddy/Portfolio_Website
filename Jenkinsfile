pipeline {
    agent any

    environment {
        // Define repository URL and branch
        REPO_URL = 'https://github.com/AnkithreddyBureddy/Portfolio_Website.git'
        BRANCH = 'main'  // Specify the branch you want Jenkins to monitor
    }

    stages {
        // Stage 1: Checkout the code from GitHub
        stage('Checkout') {
            steps {
                // Pull the code from GitHub repository
                git url: REPO_URL, branch: BRANCH
            }
        }
        
        // Stage 2: Build (Simulated step for a static website)
        stage('Build') {
            steps {
                echo 'Building the website...'
                // For a simple HTML website, this step is just a placeholder
                // You can add steps like minifying CSS/JS or other build steps if necessary
            }
        }

        // Stage 3: Run Tests (Simulated step)
        stage('Test') {
            steps {
                echo 'Running basic tests...'
                // Here you can add commands to check if files like index.html, styles.css, etc. exist
                // Or you could run basic validation for your static site
                // For example, a simple test could be checking the existence of the index.html file
                script {
                    def file = 'index.html'
                    if (!fileExists(file)) {
                        error "Test failed: ${file} not found!"
                    } else {
                        echo "${file} exists!"
                    }
                }
            }
        }

        // Stage 4: Deploy (Optional step)
        stage('Deploy') {
            steps {
                echo 'Deploying website...'
                // You can deploy the site to any platform like AWS, GCP, or any static hosting platform like GitHub Pages
                // For example, you could use AWS CLI or Firebase CLI to deploy
                // Here, just a pl
