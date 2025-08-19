pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Nothing to build, static HTML site"
            }
        }

        stage('Test') {
            steps {
                echo "Running basic checks..."
                sh 'ls -l'
                sh 'grep "<html>" index.html || exit 1'
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
