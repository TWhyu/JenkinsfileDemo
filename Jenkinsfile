pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        input {
            message "Should we continue?"
            ok "Yes, we should."
            submitter "Han"
        }
        stage('Deploy') {
            steps {
                echo 'Deploying..'
            }
        }
    }
}
