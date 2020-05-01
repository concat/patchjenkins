pipeline {
  agent none
  stages {
    stage('Patch') {
//      slackSend channel: 'ias', color: '#1e602f', message: "Please visit Jenkins server to approve this Jenkins backup"
       input {
        message "Continue to backup Jenkins server?"
        ok "Perform the Backup"
       }
  	   agent { label 'master' }
        steps {
	         withAWS(credentials: 'S3BucketAdmin', region: 'us-east-2') {
		          sh 'echo greetings from my Jenkins master'
		          sh 'echo patching my Jenkins master to save file system to s3'

              slackSend channel: 'ias', color: '#1e602f', message: "Backing up Jenkins home to s3"
//		sh 'wget -O- -q http://s3tools.org/repo/deb-all/stable/s3tools.key | apt-key add -'
//		sh 'wget -O /etc/apt/sources.list.d/s3tools.list http://s3tools.org/repo/deb-all/stable/s3tools.list'
//		sh 'apt-get update && apt-get install -y s3cmd'
		          sh 's3cmd sync /var/jenkins_home s3://beckstep1-jenkins-backups/mymaster/'
	     }
      }
    }
  }
}
