pipeline {
    agent any

    stages {

        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }

        stage("docker login") {
            steps {
                echo " ============== docker login =================="
                withCredentials([usernamePassword(credentialsId: 'test123', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                    script {
                        def loginResult = sh(script: "docker login -u $USERNAME -p $PASSWORD", returnStatus: true)
                        if (loginResult != 0) {
                            error "Failed to log in to Docker Hub. Exit code: ${loginResult}"
                        }
                    }
                }
                echo " ============== docker login completed =================="
            }
        }

        stage('run grafana') {
            steps {
                sh 'docker run -d --name=11 dimax555/jenkins:grafana-3'
            }
        }

        stage('run prometheus') {
            steps {
                sh 'docker run -d --name=12 dimax555/jenkins:prometheus-4'
            }
        }

        stage('run cadvisor') {
            steps {
                sh 'docker run -d --name=13 dimax555/jenkins:cadvisor-6'
            }
        }

        stage('run node-exporter') {
            steps {
                sh 'docker run -d --name=14 dimax555/jenkins:node-exporter-5'
            }
        }

        stage('run front') {
            steps {
                sh 'docker run -d --name=15 dimax555/web-app:frontend'
            }
        }

        stage('run back') {
            steps {
                sh 'docker run -d --name=16 dimax555/web-app:backend'
            }
        }

        stage('run database') {
            steps {
                sh 'docker run --name=17 dimax555/web-app:database'
            }
        }

    }
}
