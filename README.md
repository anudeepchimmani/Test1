pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Gangavangala07/jenkinjavaexample.git'
            }
        }
        stage('Build') {
            steps {
               
                bat 'javac PrimeNumberFinder.java'
            }
        }
        stage('Test') {
            steps {
              
                bat 'java PrimeNumberFinder'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Add your deployment commands here (like copying files to a server)
            }
        }
    }
} 
