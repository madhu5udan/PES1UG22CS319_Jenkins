pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                branches: [[name: '*/master']], 
                userRemoteConfigs: [[url: 'https://github.com/madhu5udan/PES1UG22CS319_Jenkins.git']]])
            }
        }
        stage('Build') {
            steps {
                sh 'g++ -o PES1UG22CS319-1 main/hello.cpp' // Update the path to the C++ file
            }
        }
        stage('Test') {
            steps {
                sh './PES1UG22CS319-1' // Runs the compiled file
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying the application..."
            }
        }
    }
    post {
        failure {
            echo 'Pipeline failed' // Post action in case of failure
        }
    }
}
