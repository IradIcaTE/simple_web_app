pipeline {
    agent [ label "First" ]

    statges {
        stage("Clone") {
            steps {
                git url: "", branch: 'Main'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('parth-flask-app')
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