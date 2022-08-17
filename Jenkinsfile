pipeline {
    agent any
    environment {
        ENV_URL='abc.xyz'
        SSH_CRED=credentials('SSH')
    }

    stages {
        stage('One') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Two') {
            steps {
                echo 'Welcome to DevOps'
            }
        }
    }
}
