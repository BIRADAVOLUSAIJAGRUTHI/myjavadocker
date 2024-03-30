pipeline {
    agent any
    environment {
        PATH = "C:/Windows/System32"
    }
    stages {
        stage('Test Stage') {
            steps {
                script {
                    bat '"C:\\Program Files\\Docker\\Docker\\resources\\bin\\docker.exe" info'
                }
            }
        }

        stage('Build Stage') {
            steps {
                script {
                    bat '"C:\\Program Files\\Docker\\Docker\\resources\\bin\\docker.exe" build -t myapp .'
                }
            }
        }
	    
        stage('Deploy Stage') {
            steps {
                script {
                    bat '"C:\\Program Files\\Docker\\Docker\\resources\\bin\\docker.exe" run -d --name my-java-container myapp'
                    bat '"C:\\Program Files\\Docker\\Docker\\resources\\bin\\docker.exe" logs my-java-container'
                }
            }
        }
    }
}

