1. 파일의 네 가지 종류를 간단히 설명하시오.

2. 사용자 계정의 홈 디렉토리는 무엇이며, 언제 지정하는가?


3. 다음 표에서 cd 명령의 의미를 빈칸에 쓰시오.

|명령|의미|
|---|---|
|cd ..|부모 디렉토리로 이동한다.|
|cd ../temp||
|cd ~user2||
|cd ~/temp||
|cd /tmp||

4. 파일의 종류를 구분하기 위해 ls 명령에 지정하는 옵션은 무엇인가?

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