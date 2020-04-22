pipeline {
  agent none
  stages {
    stage('Patch') {
  	agent { label 'master' }
        steps {
            sh 'echo greetings from my Jenkins master'
        }
    }
  }
}
