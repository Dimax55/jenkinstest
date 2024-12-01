pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
       stage('run grafana') {
            steps {
                sh 'docker run --name=11 dima555/jenckins:grafana-3'
            }
        }
        stage('run prometheus') {
            steps {
                sh 'docker run --name=12 dimax555/jenkins:prometheus-4'
            }
        }
        stage('run cadvisor') {
            steps {
                sh 'docker run --name=13 dimax555/jenkins:cadvisor-6'
            }
        }
        stage('run node-exporter') {
            steps {
                sh 'docker run --name=14 dimax555/jenkins:node-exporter-5'
            }
        }
        stage('run front') {
            steps {
                sh 'docker run --neme=15 dimax555/web-app:frontend'
            }
        }
        stage('run back') {
            steps {
                sh 'docker run --name16 dimax555/web-app:backend'
            }
        }
        stage('run database') {
            steps {
                sh 'docker run --name=17 dimax555/web-app:database'
            }
        }


    }
}
