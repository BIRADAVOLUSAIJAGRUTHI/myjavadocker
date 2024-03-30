pipeline {
    agent any
    environment {
        PATH = "C:/Windows/System32"
    }
    stages {
        stage('Test Stage') {
            steps {
                script {
                    bat 'docker info'
                }
            }
        }

        stage('Build Stage') {
            steps {
                script {
                    sh 'docker build -t myapp .'
                }
            }
        }

        stage('Deploy Stage') {
            steps {
                script {                    bat 'docker run -d --name my-java-container myapp'
                    // Fetch the output of the java script
		    bat 'docker logs my-java-container'
                }
            }
        }
    }
}

