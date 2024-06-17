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
// deploy steps
}
}
}
}