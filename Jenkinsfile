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
cd /var/lib/jenkins/workspace/ami_master/packer/build_awslinux2
/opt/packer/packer build gitlab-ami.json
        '''
      }
    }

  }
  environment {
    GIT_BRANCH = 'master'
    OS_Type = 'awslinux2'
    Target_Image = 'gitlab'
  }
  parameters {
    string(name: 'OS_Type', defaultValue: 'awslinux2', description: 'awslinux2 | ubuntu')
    string(name: 'Target_Image', defaultValue: 'gitlab', description: 'gitlab | jenkins | sonarqube')
    string(name: 'branch', defaultValue: 'master', description: 'branch name')
  }
}