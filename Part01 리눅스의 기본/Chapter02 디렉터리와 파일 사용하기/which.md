* 명령어 파일의 위치를 찾아서 그 경로나 alias를 출력
* alias를 먼저 찾고 그 다음 PATH 환경 변수에 지정된 경로를 찾음

```shell
[root@linux1 ch2]# which mv
alias mv='mv -i'
	/usr/bin/mv
[root@linux1 ch2]# 
```