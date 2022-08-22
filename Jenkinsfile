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
                when {branch pattern: "feature-.*", comparator: "REGEXP"}
            steps {
                echo "Hello ${params.PERSON}"
            }
        }
            stage('Two') {
            steps {
                echo "Welcome to DevOps"
            }
        }
            stage('Three') {
                when {branch 'main'}
                steps {
                    sh "ansible-playbook ping-test.yaml -e ansible_user=${SSH_CRED_USR} -e ansible_ssh_password=${SSH_CRED_PSW} -i inventory.txt"
            }
        }
        }
    }
}
}