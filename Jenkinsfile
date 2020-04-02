pipeline {
  agent any
  stages {
    stage('Git clone') {
      steps {
        git(url: 'https://github.com/opsflex/ami.git', branch: 'master')
      }
    }

    stage('Image Build') {
      steps {
        sh '''
cd /var/lib/jenkins/workspace/ami_master
/opt/packer/packer build packer/build_ubuntu/gitlab-ami.json
        '''
      }
    }

  }
}
