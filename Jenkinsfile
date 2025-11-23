pipeline {
    agent any

    // 1. Define Tools (matches the name in 'Manage Jenkins > Tools')
    tools {
        maven 'Maven'
    }

    // 2. Define Parameters
    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run Tests?')
    }

    // 3. Define Environment Variables
    environment {
        NEW_VERSION = '1.3.0'
    }

    stages {
        stage('Build') {
            steps {
                echo "Building version ${NEW_VERSION}"
                // Linux Command: 'sh' instead of 'bat'
                sh 'mvn -version'
            }
        }

        stage('Test') {
            // 4. Conditional Execution
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

    // 5. Post-build Actions
    post {
        always {
            echo 'Pipeline Completed'
        }
    }
}
