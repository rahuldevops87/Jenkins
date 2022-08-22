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
            stage('Three') {
                steps {
                    sh "ansible-playbook ping-test.yaml -e ansible_user=${SSH_CRED_USR} -e ansible_ssh_password=${SSH_CRED_PSW} -i inventory.txt"
            }
        }
        }
    }
}
}