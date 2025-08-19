pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm   // pulls your repo code (from GitHub)
            }
        }

        stage('Build') {
            steps {
                echo "Nothing to build, static HTML site"
            }
        }

        stage('Test') {
            steps {
                echo "Checking if index.html exists..."
                sh 'test -f index.html'   // verifies index.html file is present
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying to Apache web server..."
                sh '''
                sudo rm -rf /var/www/html/*
                sudo cp -r * /var/www/html/
                '''
            }
        }
    }
}

