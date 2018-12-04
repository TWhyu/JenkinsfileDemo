pipeline {
  agent none
  stages{
    stage('Release?') {
    agent none
    options {
      // Optionally, let's add a timeout that we don't allow ancient
      // builds to be released.
      timeout time: 21, unit: 'DAYS' 
    }
    steps {
      script {
        env.DO_RELEASE = input(
            id: 'userInput', message: 'Ready to go?',
            parameters: [
                string(
                    defaultValue: 'No',
                    description: 'Ready for release',
                    name: 'userInput'
                )
            ]
        )
      }
      milestone 1
    }
  }
    stage('Release') {
    agent any
    when {
      beforeAgent true
      environment name: 'DO_RELEASE', value: 'yes'
    }
    steps {
      lock('release') {
        milestone 2
        echo "release...!"
      }
    }
  }   
  }
}
