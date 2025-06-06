pipeline {
    agent { label "First" }

    stages {
        stage("Clone") {
            steps {
                git url:"https://github.com/IradIcaTE/simple_web_app.git", branch: 'main'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t parth-flask-app .'

                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker run -d -p 5000:5000 --name flash_app parth-flask-app'
                }
            }
        }
    }
}