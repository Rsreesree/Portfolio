pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checkout Stage'
                sh 'echo Checkout Done'
            }
        }

        stage('Build') {
            steps {
                echo 'Build Stage'
                sh 'echo Build Done'
            }
        }

        stage('Test') {
            steps {
                echo 'Test Stage'
                sh 'exit 1'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy Stage'
                sh 'echo Deploy Done'
            }
        }
    }
}
