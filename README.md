# linux
CentOS 사용법 

-해당 내용은 CentOS 7 버전으로 설명합니다.<br>
-추가적인 내용은 공부하면서 업데이트 될 예정입니다.

# 1. 설치

CentOS를 설치하기위해서는 ISO를 다운받아야 합니다. 

http://mirror.kakao.com/centos/7.9.2009/isos/x86_64/

![image](https://user-images.githubusercontent.com/42128097/153798752-f4cb9b29-46ec-4ff7-b85f-8f82002b2e24.png)


작성자는 minimal 버전으로 다운받았다 (CentOS-7-x86_64-Minimal-2009.iso)<br>
해당 차이에 대해서는 간략하게 설명하자면 UI가 있는 CentOS 를 사용할것인지 아닌지의 차이.

minimal버전은 UI가 없다.

windows에서의 원활한 진행을 위해 아래 virtualbox 를 다운받아주자.

https://www.virtualbox.org/wiki/Downloads

물론 windows에서 사용할 예정이기 때문에 windows hosts로 다운받으면 된다.

virtual머신은 CentOS로 잡아주고 다운받은 ISO파일을 광학드라이버에 인식해준다.

네트워크 설정은 어뎁터에 브릿지로 잡아준다.

# 2. 네트워크 설정 

초기 CentOS를 설치했으면 네트워크 설정을 해줘야한다. <br>
네트워크 설정은 주로 
cd /etc/sysconfig/network-scripts/ 에서 설정하며, ifcfg~~ 를 vi에디터로 열어주면 된다. 

<li>BOOTPROTO="static"</li>
<li>IPADDR="할당할 아이피"</li>
<li>NETMASK="넷마스크"</li>
<li>GATEWAY="게이트웨이"</li>


를 추가적으로 작성을 해주면된다. 

해당 내용은 본인이 사용하는 인터넷을 확인해보면 된다.

추가적으로 editplus에서 연결을 확인해볼수 있으며<br>
windows 프로그램인 OpenSSH 로 cmd를 통해 연결을 해볼 수 있다. 
(보안으로 인해 OpenSSH로 접속은 많이는 사용안하는편)

cmd를 통해 OpenSSH로 접속방법은 cmd내에서 

cd C:\Windows\System32\OpenSSH 로 접속 후 <br>
ssh root@(linux server ip)<br>
password <br>

해당 작업 후 접속이 되었다면 성공
<br>
<br>
- sudu systemctl start network   - 네트워크 실행 <br>
- sudu systemctl restart network - 네트워크 재시작 <br>
- sudu systemctl stop network    - 네트워크 종료

# 3.방화벽
현 firewall 가 어떤 상태인지 알아야합니다. 

firewall-cmd --state<br>해당 명령어로 구동이 되고있는지 확인할 수 있습니다.

기본적으로 방화벽이 설치되어있는 경우도있지만, 설치가 안되어있다면 <br>
yum install furewalld 명령어로 다운로드 받을 수 있습니다. <br>
root 계정이 아니라면 sudu yum install firewalld 명령어를 사용하면 됩니다.<br>

- systemctl start firewalld 방화벽 시작 명령어
- systemctl stop firewalld 방화벽 종료 명령어
