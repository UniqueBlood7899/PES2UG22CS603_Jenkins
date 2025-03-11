pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: '**/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/UniqueBlood7899/PES2UG22CS603_Jenkins.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                build 'PES2UG22CS603-1'
                sh 'g++ hello.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
