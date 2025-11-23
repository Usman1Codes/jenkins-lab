pipeline {
    agent any
    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Uncheck to skip tests')
    }
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
                sh 'mvn -version'
            }
        }
        stage('Test') {
            // This stage only runs if the checkbox is TRUE
            when {
                expression { params.executeTests == true }
            }
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
