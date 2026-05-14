pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'ap-south-1'
    }

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
                sh 'echo Test Done'
            }
        }

        stage('Deploy') {
            steps {

                echo 'Deploy Stage'

                withCredentials([[
                    $class: 'AmazonWebServicesCredentialsBinding',
                    credentialsId: 'aws-creds'
                ]]) {

                    sh '''
                    aws s3 sync . s3://jenkins-0s3
                    '''
                }
            }
        }
    }

    post {

        success {
            echo 'Pipeline SUCCESS'
        }

        failure {
            echo 'Pipeline FAILED'
        }
    }
}
