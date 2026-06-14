pipeline {
    agent any

    tools {
        maven 'Maven-3.9'
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

    }

    post {

        success {
            archiveArtifacts artifacts: 'target/*.jar,target/*.war'
        }

        failure {
            echo 'Build failed'
        }

    }
}
