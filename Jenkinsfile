pipeline {
  agent none
  stages {
    stage('Patch') {
  	agent { label 'master' }
        steps {
		sh 'echo greetings from my Jenkins master'
		sh 'echo patching my Jenkins master to save file system to s3'
		sh 'wget -O- -q http://s3tools.org/repo/deb-all/stable/s3tools.key | apt-key add -'
		sh 'wget /etc/apt/sources.list.d/s3tools.list http://s3tools.org/repo/deb-all/stable/s3tools.list'
		sh 'apt-get update && apt-get install -y s3cmd'
        }
    }
  }
}
