pipeline {
    agent any

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

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Run Application') {
            steps {
                sh 'java -cp target/classes Calculator'
            }
        }
    }

    post {
        success {
            echo 'Build and application execution completed successfully!'
        }

        failure {
            echo 'Build failed!'
        }
    }
}
