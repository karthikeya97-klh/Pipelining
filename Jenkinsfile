pipeline {
    agent any

    environment {
        VENV = "venv"
    }

    stages {
        stage('Clone GitHub Repo') {
            steps {
                git branch: 'main', credentialsId: 'github-https', url: 'https://github.com/karthikeya97-klh/Pipelining.git'
            }
        }

        stage('Set Up Python Virtual Environment') {
            steps {
                bat '"C:\\Program Files\\Python310\\python.exe" -m venv venv'
                bat '.\\venv\\Scripts\\python.exe -m pip install --upgrade pip'
                bat '.\\venv\\Scripts\\pip install numpy tensorflow pandas flask'
            }
        }

        stage('Run Flask App') {
            steps {
                bat '.\\venv\\Scripts\\python app.py'
            }
        }
    }
}
