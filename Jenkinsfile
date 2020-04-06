pipeline {
  agent any
  stages {
    stage('Git clone') {
      steps {
        git(url: 'https://github.com/opsflex/ami.git', branch: "${GIT_BRANCH}")
      }
    }

    stage('Image Build') {
      steps {
        sh '''
cd /var/lib/jenkins/workspace/ami_master/packer/build_${OS_Type}
/opt/packer/packer build ${Target_Image}-ami.json
        '''
      }
    }

  }
  environment {
    GIT_BRANCH = 'master'
    OS_Type = 'ubuntu'
    Target_Image = 'jenkins'
  }
}