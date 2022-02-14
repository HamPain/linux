# linux
CentOS 사용법 

-해당 내용은 CentOS 7 버전으로 설명합니다.

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
