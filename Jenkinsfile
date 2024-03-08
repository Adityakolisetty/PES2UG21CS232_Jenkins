pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: "GitSCM",
                          branches: [[name: 'main']],
                          userRemoteConfigs: [[url: 'https://github.com/Adityakolisetty/PES2UG21CS232_Jenkins.git']]])
            }
        }
        stage('Build') {
            steps {
                build PES2UG21CS232-1
                sh 'g++ main.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deployment...'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
