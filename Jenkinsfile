pipeline {
    agent any
    environment {
        PATH1 = "C:/Windows/System32"
	PATH2 = "C:/Program Files/Git/bin/git.exe"
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

