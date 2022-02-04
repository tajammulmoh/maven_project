pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/mohdadil82/mvnproj.git'
            }
        }
        stage('Build') {
            steps {
                // build maven project
                sh "mvn -Dmaven.test.failure.ignore=true clean package"

            }
        }
        stage('Build docker image and run container') {
            steps {
                // build maven project
                sh 'docker build -t catalina:latest .'
                sh 'docker run -d -p 8090:8080 catalina'
            }
        }
    
    }
}
