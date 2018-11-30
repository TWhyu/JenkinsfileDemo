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
        timeout(time:5, unit:'SECONDS') {
            input message:'Approve deployment?', submitter: 'han'
        }
        stage('Deploy') {
            steps {
                echo 'Deploying..'
            }
        }
    }
}
