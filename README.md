# aws-devstack

## 준비물
AWS 계정

## 사용법
※ 경고 잘못 사용 하다가 과금이 됩니다.
1. https://console.aws.amazon.com/ec2/에서 Amazon EC2 콘솔을 열어 로그인합니다.</br>

2. 콘솔 대시보드에서 인스턴스 시작을 선택합니다.</br>

3. Amazon Machine Image(AMI) 선택 페이지에 인스턴스에 대한 템플릿 역할을 하는 Amazon Machine Image(AMI)라는 기본 구성 목록이 표시됩니다. Ubuntu Server 16.04 LTS (HVM), SSD Volume Type을 선택합니다.

4. 인스턴스 유형 선택 페이지에서 인스턴스의 하드웨어 구성을 선택할 수 있습니다. t2.xlarge 유형을 선택합니다.</br>

5. 인스턴스 세부 정보 구성 디폴트 설정으로 다음: 스토리지 추가를 클릭하세요.</br>

6. 스토리지 추가에서는 넉넉하게 100GiB로 수정하여 다음: 태그 추가를 클릭합시오.</br>

7. 태그 추가도 디폴트 설정으로 다음: 보안 그룹 구성을 클릭하십시오.</br>

8. 유형을 모든 TCP와 소스를 0.0.0.0/0로 설정하여 검토 및 시작를 클릭하십시오.</br>

9. 검토에서는 시작하기를 클릭하십시오.</br>

10. 기존 키 페어 선택 또는 새 키 페어 생성에서는 생성을 하거나 기존에 있던 키를 선택하여 pem를 사용하십시오.

11. SSH를 username은 ubuntu입니다.

12. 인스턴스가 생성이 되면 다음과 같이 명령어를 기입해 주세요.</br>
`sudo apt-get update; sudo apt-get updgrade; sudo apt-get dist-upgrade`</br>
`sudo reboot`</br>
`sudo -i`</br>
`adduser stack`</br>
`usermod -aG sudo stack`</br>
`echo "stack ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers`</br>
`su - stack`</br>
`sudo apt-get install git`</br>
`git clone https://github.com/openstack-dev/devstack`</br>
`cp devstack/samples/local.conf ~/devstack/`</br>
`cd devstack/`</br>
`ls`</br>
`sudo nano local.conf`</br>
`ADMIN_PASSWORD=1234`</br>
`DATABASE_PASSWORD=1234`</br>
`RABBIT_PASSWORD=1234`</br>
`SERVICE_PASSWORD=1234`</br>
`echo "enable_plugin sahara git://github.com/openstack/sahara" >> local.conf`</br>
`echo "enable_plugin sahara-dashboard git://github.com/openstack/sahara-dashboard" >> local.conf`</br>
`echo "enable_plugin ceilometer git://github.com/openstack/ceilometer" >> local.conf`</br>
`./stack.sh`

12. 20분 정도 기다리시면 데브스택이 됩니다.

## 결과
AWS에서 DevStack를 사용할 수 있습니다.
