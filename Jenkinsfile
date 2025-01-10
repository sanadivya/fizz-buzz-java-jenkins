pipeline {
    agent any

     tools {
        maven 'MAVEN' // Name of the Maven configuration in Jenkins
    }
    
    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven_3_5_0') {
                    bat 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven_3_5_0') {
                    bat 'mvn test'
                }
            }
        }

        // stage ('Deployment Stage') {
        //     steps {
        //         withMaven(maven : 'maven_3_5_0') {
        //             bat 'mvn deploy'
        //         }
        //     }
        // }
    }
}