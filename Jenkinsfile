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
cd /var/lib/jenkins/workspace/ami_master/packer/build_ubuntu
/opt/packer/packer build gitlab-ami.json
        '''
      }
    }

  }
}
