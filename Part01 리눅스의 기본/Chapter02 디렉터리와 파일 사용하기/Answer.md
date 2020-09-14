1. 파일의 네 가지 종류를 간단히 설명하시오.
   * 일반 파일 : 텍스트 파일, 실행 파일, 이미지 파일 등 리눅스에서 사용하는 대부분의 파일
   * 디렉토리 파일 : 해당 디렉터리에서 저장된 파일이나 하위 디렉터리에 대한 정보
   * 링크 파일
     * 하드 링크 : 파일 시스템의 파일의 이름과 연결되는 디렉터리 엔트리
     https://ko.wikipedia.org/wiki/%ED%95%98%EB%93%9C_%EB%A7%81%ED%81%AC
     * 심볼릭 링크 : 절대 경로 또는 상대 경로의 형태로 된 다른 파일이나 디렉터리에 대한 참조를 포함하고 있는 특별한 종류의 파일
     https://ko.wikipedia.org/wiki/%EC%8B%AC%EB%B3%BC%EB%A6%AD_%EB%A7%81%ED%81%AC
   * 장치 파일 : 유닉스 계열 운영 체제에서 마치 흔한 파일처럼 보이는 파일 시스템 안에 보이는 장치 드라이버의 인터페이스
     https://ko.wikipedia.org/wiki/%EC%9E%A5%EC%B9%98_%ED%8C%8C%EC%9D%BC

2. 사용자 계정의 홈 디렉토리는 무엇이며, 언제 지정하는가?

시스템의 사용자에게 주어진 파일들을 포함한 다중 사용자 운영 체제의 파일 시스템 디렉토리를 의미한다.
사용자 계정이 생성 되었을때 생성 된다.
```shell
useradd -m 계정명
```

3. 다음 표에서 cd 명령의 의미를 빈칸에 쓰시오.

|명령|의미|
|---|---|
|cd ..|부모 디렉토리로 이동한다.|
|cd ../temp|상위 디렉토리에 있는 temp 디렉토리로 이동한다.|
|cd ~user2|user2의 홈 디렉터리로 이동한다.|
|cd ~/temp|자신의 홈 디렉터리에서 하위의 temp 디렉토리로 이동한다.|
|cd /tmp|루트 디렉터리에 있는 tmp 디렉토리로 이동한다.|

```shell
[root@linux1 ~]# cd ..
[root@linux1 /]# pwd
/
[root@linux1 /]#
```

```shell
[root@linux1 /]# cd ../temp
[root@linux1 temp]# pwd
/temp
[root@linux1 temp]# 
```

```shell
[root@linux1 temp]# cd ~user2
[root@linux1 user2]# pwd
/home/user2
[root@linux1 user2]# 
```

```shell
[root@linux1 user2]# cd ~/temp
[root@linux1 temp]# pwd
/root/temp
[root@linux1 temp]# 
```

```shell
[root@linux1 temp]# cd /tmp
[root@linux1 tmp]# pwd
/tmp
[root@linux1 tmp]# 
```

4. 파일의 종류를 구분하기 위해 ls 명령에 지정하는 옵션은 무엇인가?
```shell
[root@linux1 ~]# ls -F
abc.txt          f1              file1                 linux_ex/  test1.txt  user1/     문서/      사진/
anaconda-ks.cfg  file-16-16.txt  file2                 list0.txt  tmp1/      공개/      바탕화면/  서식/
err1.txt         file-16-18.txt  initial-setup-ks.cfg  temp/      tmp2/      다운로드/  비디오/    음악/
[root@linux1 ~]# 
```

|표시|의미|
|---|---|
||파일|
|*|실행파일|
|/|디렉토리|
|=|소켓|
|@|심볼릭 링크|

5. ls 명령으로 파일의 종류를 구분하여 출력했더니 파일명 끝에 @이 추가되었다. 이것은 무엇을 의미하는가?

6. .(마침표)로 시작하는 파일은 무엇이며, 이 파일을 확인하려면 어떻게 해야 하는가?

7. ls / 명령은 루트 디렉토리의 내용을 보여준다. 루트 디렉토리 자체의 정보를 확인하려면 어떻게 해야 하는가?

8.  절대 경로와 상대 경로를 정의하시오.

9. 하드 링크와 심볼릭 링크, 복사 파일을 비교하여 설명하시오.

10. rmdir 명령과 rm -r 명령의 차이를 설명하시오.

11. temp 디렉토리를 생성한 후 ls -al 명령으로 temp 디렉토리의 내용을 확인했더니 다음과 같이 출력되었다. 현재 디렉토리(.)의 하드 링크 값이 2인 이유를 설명하시오.

```shell
[root@linux1 ~]# ls -al temp
합계 4
drwxr-xr-x.  2 root root   17  9월  6 16:08 .
dr-xr-x---. 2 root root 4096  9월 14 09:08 ..
[root@linux1 ~]#
```

12. 심볼릭 링크 A의 원본 파일인 B를 삭제한 후 C 파일을 B로 복사했다. 심볼릭 링크 A의 내용을 출력했을 때 어느 파일의 내용이 출력되는가? 왜 그런지 설명하시오.

13. cp a.txt b.txt c.txt temp는 무엇을 실행하는 명령인가? 여기서 temp는 무엇이어야 하는가?

14. inode에 대해 간단히 설명하시오.

15. 파일명은 다른데 inode가 같다는 것은 무엇을 의미하는가?

16. 현재 디렉토리가 ch2일 때 다음 표의 빈칸을 채우시오.

|파일|절대 경로명|상대 경로명
|---|---|---|
|/|||
|lib|||
|data1|||
|test|||
|hosts|||

17. 현재 디렉토리를 lib 디렉토리로 이동하는 명령은 무엇인가?

18. rmdir 명령으로 ch2 디렉토리를 삭제하려고 한다. 삭제되는지 확인하고, 삭제되지 않으면 그 이유를 설명하시오.

19. pwd 명령을실행하니 현재 위치가 /home/user1/ch2였다. data1 파일의 내용을 행 번호를 붙여서 출력하는 명령은 무엇인가?

20. 현재 디렉토리에 data1 파일의 하드 링크를 data1-hard라는 이름으로 만드는 명령은 무엇인가?

21. 현재 디렉토리에 ch2 디렉토리의 심볼릭 링크를 ch2-sym이라는 이름으로 만드는 명령은 무엇인가?

22. /etc/passwd 파일에서 문자열 'bash'가 들어 있는 행을 출력하시오.

23. /etc 다렉토리 아래에 있는 passwd 파일의 경로를 찾으시오.

24. cp의 실행 파일이 있는 위치를 검색하시오.