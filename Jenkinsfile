pipeline {
    agent any
    stages {
        stage('Rezando') {
            steps {
                echo 'Rezando a los dioses de DevOps...'
            }
        }
        stage('Checkout') {
            steps {
                git 'https://github.com/Cirorx/DevOps-Tarea-Individual-S3'
            }
        }
        stage('Buildear imagen') {
            steps {
                script {
                    def appImage = docker.build("mi-flask-app:${env.BUILD_ID}")
                }
            }
        }
        stage('Ejecutar Docker ') {
            steps {
                script {
                    docker.image("mi-flask-app:${env.BUILD_ID}").run('-d -p 5000:5000')
                }
            }
        }
        stage('Alivio') {
            steps {
                echo 'Contenedor con Flask fue creado'
            }
        }
    }
}
