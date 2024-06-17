pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/minseoBae/apridsdemo.git', credentialsId: 'minseo'
               }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                    sh 'chmod 755 ./gradlew'
                    sh './gradlew build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // test steps
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                withAWS(credentials: 'aws_minseo') {
                    sh 'aws s3 cp build/libs/apirdsdemo_build-0.0.1-SNAPSHOT.jar s3://minseo-build-files/'
                }
            }
        }
    }
}