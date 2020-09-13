1. /etc/passwd 파일에서 문자열 'user1'이 있는 행을 검색
```shell
[root@linux1 ch2]# grep -n user1 /etc/passwd
48:user1:x:1001:1001::/home/user1:/bin/bash
[root@linux1 ch2]# 
```

2. find 명령으로 홈 디렉토리에서 data1.ln 파일을 검색
```shell
[root@linux1 ch2]# find ~ -name data1.ln
/root/linux_ex/ch2/data1.ln
[root@linux1 ch2]# 
```

3. find 명령으로 홈 디렉토리에서 data1.ln 파일을 찾아 data1로 복사
```shell
[root@linux1 ch2]# find ~ -name data1.ln -exec cp {} data1 \;
[root@linux1 ch2]# ls
data  data1  data1.ln  data1.sl  temp  test
[root@linux1 ch2]# 
```