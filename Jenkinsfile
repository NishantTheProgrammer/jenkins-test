pipeline {
    agent any  // This defines where the pipeline should run (any available agent)

    triggers {
        // This triggers the pipeline when changes are pushed to the main branch
        pollSCM('H/5 * * * *')  // Check for changes in SCM every 5 minutes
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the repository code
                git branch: 'main', url: 'https://your-repository-url.git'
            }
        }

        stage('Build') {
            steps {
                // Example build step, you can replace with your own build commands
                echo 'Building project...'
                // Example: sh 'mvn clean install'  // if you're using Maven
            }
        }

        stage('Test') {
            steps {
                // Example test step
                echo 'Running tests...'
                // Example: sh 'mvn test'  // if you're using Maven for tests
            }
        }

        stage('Deploy') {
            steps {
                // Example deploy step
                echo 'Deploying project...'
                // Example: sh './deploy.sh'  // your deployment script
            }
        }
    }

    post {
        success {
            echo 'Build and deployment were successful!'
        }
        failure {
            echo 'Something went wrong with the build or deployment.'
        }
    }
}
