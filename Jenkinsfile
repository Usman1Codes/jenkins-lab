pipeline {
    agent any
    tools {
        maven 'Maven'
    }
    environment {
        NEW_VERSION = '1.3.0'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building version ${NEW_VERSION}"
                // Using 'sh' because you are on Ubuntu Linux
                sh 'mvn -version'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing Project...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying Project...'
            }
        }
    }
    post {
        always {
            echo 'Pipeline Completed successfully!'
        }
    }
}
