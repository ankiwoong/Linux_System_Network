1. /etc/services 파일에서 문자열 'MacOS'가 있는 행을 찾아 행 번호와 함께 출력
```shell
[root@linux1 ch2]# grep -n MacOS /etc/services
1437:mac-srvr-admin  660/tcp                 # MacOS Server Admin
1438:mac-srvr-admin  660/udp                 # MacOS Server Admin
[root@linux1 ch2]# 
```

2. 홈 데릭토리에서 파일명이 data1.cp인 파일이 잇는지 검색
```shell
[root@linux1 ch2]# find ~ -name data1.cp
/root/linux_ex/ch2/data1.cp
[root@linux1 ch2]#
```

3. 홈 디렉토리에서 파일명이 data1.cp인 파일을 찾아 temp 디렉토리로 이동
```shell
[root@linux1 ch2]# find ~ -name data1.cp -exec mv {} temp \;
[root@linux1 ch2]# ls temp
data1.cp  data2  hosts  services  text1  text2
[root@linux1 ch2]# 
```