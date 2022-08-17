pipeline {
    agent any
    parameters {
        string {name: 'PERSON', defaultValue: 'Mr. Jenkins', description: 'Please enter a name'}
    }
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
