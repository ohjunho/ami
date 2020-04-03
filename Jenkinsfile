pipeline {
  agent any
  parameters {
      string(name : 'OS_Type', defaultValue : 'awslinux2', description : 'awslinux2 | ubuntu')
      string(name : 'Target_Image', defaultValue : 'gitlab', description : 'gitlab | jenkins | sonarqube')
      string(name : 'branch', defaultValue : 'master', description : 'branch name')
  }
  stages {
    stage('Git clone') {
      steps {
        git(url: 'https://github.com/opsflex/ami.git', branch: "${branch}")
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
}
