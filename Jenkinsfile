pipeline {
    agent any

     tools {
        maven 'MAVEN' // Name of the Maven configuration in Jenkins
    }

    stages {
       stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
         stage('Install Vercel CLI') {
            steps {
                bat 'npm install -g vercel' // Installs Vercel CLI
            }
        }

        stage('Deploy to Vercel') {
            steps {
                withCredentials([string(credentialsId: 'VERCEL_TOKEN', variable: 'MY_VERCEL_TOKEN')]) {
                    bat 'npx vercel --prod --token %MY_VERCEL_TOKEN% --yes --name fizz-buzz-java-jenkins'
                //bat 'vercel deploy --prod --token %VERCEL_TOKEN%'
                }
            }
        }
    }
}