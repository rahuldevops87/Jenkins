pipeline {
    agent any
    parameters {
        string (name: 'PERSON', defaultValue: 'Mr. Jenkins', description: 'Please enter a name')
    }
    environment {
        ENV_URL='abc.xyz'
        SSH_CRED=credentials('SSH')
    }

    stages {
        stage('Parallel stages') {
        parallel {
            stage('One') {
            steps {
                echo "Hello ${params.PERSON}"
            }
        }
            stage('Two') {
            when {branch 'test'}
            steps {
                echo "Welcome to DevOps"
            }
        }
        }
    }
}
