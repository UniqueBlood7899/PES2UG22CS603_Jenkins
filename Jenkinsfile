pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                checkout([$class: 'GitSCM',
                branches: [[name='*/main']],
                userRemoteConfigs: [[url:'https://github.com/UniqueBlood7899/PES2UG22CS603_Jenkins.git']]])
            }}   
        stage('Build') {
            steps {
                build 'PES2UG22CS603-1'
                sh 'g++ hello.cpp -o hello_exec'
            }
        }
        stage('Test') {
            steps {
                sh './hello_exec'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying Application...'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline Failed'
        }
    }
}
