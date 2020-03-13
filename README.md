# Packer + Ansible Toolchain (304 test)

## 빌드 및 AMI 생성 확인
### 1. AWS Confiture
    cmd $aws configure
        <AWS Access Key ID> 입력
        <AWS Secret Access Key> 입력
        Default region name: 'ap-northeast-2' 입력
    
### 2. Packer bild
    cmd $ cd ~
    cmd $ mkdir workspace
    cmd $ cd workspace
    
    /* git clone */
    cmd $ git clone https://github.com/opsflex/ami.git
    cmd $ cd ~/workspace/ami/packer
    
    /* packer build */
    packer build default.json
    
## 생성된 이미지 확인
### 1. AWS Console 로그인
#### https://console.aws.amazon.com/   

### 2. AMI 확인
#### 서비스 > EC2 > 이미지 > AMI 에서 생성된 이미지 확인   

### 3. AMI 로 EC2 인스턴스 생성
#### 생성된 이미지 선택 > '시작하기' 버튼을 클릭하여 EC2 인스턴스 생성   

### 4. EC2 인스턴스에서 설치된 항목 확인
#### 생성된 EC2에 접속하여 설치 리스트 확인   