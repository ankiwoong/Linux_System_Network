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

심볼릭 링크 파일을 의미한다.
윈도우의 바로가기처럼 원본 파일을 가리키는 파일을 의미한다.

```shell
[root@linux1 ch2]# ls -F
data  data1  data1.ln  data1.sl@  temp/  test
[root@linux1 ch2]#
```

6. .(마침표)로 시작하는 파일은 무엇이며, 이 파일을 확인하려면 어떻게 해야 하는가?

.(마침표)로 시작하는 파일 : 숨겨진 파일

```shell
[root@linux1 ~]# ls -a
.              .bashrc    .lesshst  abc.txt          file1                 test1.txt  문서
..             .cache     .local    anaconda-ks.cfg  file2                 tmp1       바탕화면
.ICEauthority  .config    .pki      err1.txt         initial-setup-ks.cfg  tmp2       비디오
.bash_history  .cshrc     .ssh      f1               linux_ex              user1      사진
.bash_logout   .dbus      .tcshrc   file-16-16.txt   list0.txt             공개       서식
.bash_profile  .esd_auth  .viminfo  file-16-18.txt   temp                  다운로드   음악
[root@linux1 ~]# 
```

7. ls / 명령은 루트 디렉토리의 내용을 보여준다. 루트 디렉토리 자체의 정보를 확인하려면 어떻게 해야 하는가?

```shell
[root@linux1 ~]# ls /
bin   dev  home  lib64  mnt  proc  run   srv  temp  tree   usr  work
boot  etc  lib   media  opt  root  sbin  sys  tmp   user1  var
[root@linux1 ~]# 
```

```shell
[root@linux1 ~]# ls -d
.
[root@linux1 ~]# 
```

```shell
[root@linux1 ~]# ls -ld
dr-xr-x---. 21 root root 4096  9월 14 09:08 .
[root@linux1 ~]# 
```

8. 절대 경로와 상대 경로를 정의하시오.
* 절대 경로 : 최상위 디렉토리 (/)부터 시작해서 목표 디렉토리까지 가는 경로를 전부 기술하는 방식
* 상대 경로 : 현재 자신이 있는 위치를 기준으로 이동을 하는 방식

9. 하드 링크와 심볼릭 링크, 복사 파일을 비교하여 설명하시오.
* 하드 링크
  * 원본 파일과 동일한 inode를 가진다.
  * 원본 파일이 삭제 되더라도 원본 파일의 inode를 갖고 있는 링크 파일은 여전히 사용 가능하다.
```shell
[root@linux1 ch2]# ln test test_hard
[root@linux1 ch2]# ls -ali
합계 688
18124022 drwxr-xr-x. 3 root root    104  9월 14 12:36 .
 1520947 drwxr-xr-x. 3 root root     17  9월  6 16:39 ..
18124020 -rw-r--r--. 2 root root     12  9월 14 12:36 test
18124020 -rw-r--r--. 2 root root     12  9월 14 12:36 test_hard
[root@linux1 ch2]# 
```

* 심볼릭 링크
  * 원본 파일의 이름을 가르키는 링크.
  * 원본 파일이 삭제 되면 사용을 할 수 없다.(바로가기 개념)
```shell
[root@linux1 ch2]# ln -s test test_symbolic
[root@linux1 ch2]# ls -ali
합계 688
18124022 drwxr-xr-x. 3 root root    125  9월 14 12:41 .
 1520947 drwxr-xr-x. 3 root root     17  9월  6 16:39 ..
18124020 -rw-r--r--. 2 root root     12  9월 14 12:36 test
18111955 lrwxrwxrwx. 1 root root      4  9월 14 12:41 test_symbolic -> test
[root@linux1 ch2]# 
```

* 복사 파일
  * 파일을 완전 복사하여 다른 파일을 만든다.
  * 하드링크와 다르게 inode값이 다른것을 확인 할 수 있다.
```shell
[root@linux1 ch2]# cp test test_copy
[root@linux1 ch2]# ls -ali
합계 692
18124022 drwxr-xr-x. 3 root root    143  9월 14 12:43 .
 1520947 drwxr-xr-x. 3 root root     17  9월  6 16:39 ..
18124020 -rw-r--r--. 2 root root     12  9월 14 12:36 test
18111960 -rw-r--r--. 1 root root     12  9월 14 12:43 test_copy
[root@linux1 ch2]# 
```

10. rmdir 명령과 rm -r 명령의 차이를 설명하시오.
* rmdir
  * 비어있는 디렉토리를 삭제
  * 비어있지 않으면 삭제가 안된다.
```shell
[root@linux1 ch2]# tree test_d
test_d
├── a
├── b
└── c

0 directories, 3 files
[root@linux1 ch2]# rmdir test_d
rmdir: failed to remove 'test_d': 디렉터리가 비어있지 않음
[root@linux1 ch2]# 
```

* rm -r
  * 비어있지 않은 디렉토리를 삭제
```shell
[root@linux1 ch2]# tree test_d
test_d
├── a
├── b
└── c

0 directories, 3 files
[root@linux1 ch2]# rm -r test_d
rm: descend into directory 'test_d'? y
rm: remove 일반 빈 파일 'test_d/a'? y
rm: remove 일반 빈 파일 'test_d/b'? y
rm: remove 일반 빈 파일 'test_d/c'? y
rm: remove 디렉토리 'test_d'? y
[root@linux1 ch2]# ll
합계 692
-rw-r--r--. 1 root root 692252  9월 13 17:32 data
-rw-r--r--. 1 root root      0  9월 13 20:48 data1
-rw-r--r--. 1 root root      0  9월 12 21:02 data1.ln
lrwxrwxrwx. 1 root root      5  9월 13 12:28 data1.sl -> data1
drwxr-xr-x. 2 root root     90  9월 13 20:38 temp
-rw-r--r--. 2 root root     12  9월 14 12:36 test
-rw-r--r--. 1 root root     12  9월 14 12:43 test_cpopy
-rw-r--r--. 2 root root     12  9월 14 12:36 test_hard
lrwxrwxrwx. 1 root root      4  9월 14 12:41 test_symbolic -> test
[root@linux1 ch2]# 
```

11. temp 디렉토리를 생성한 후 ls -al 명령으로 temp 디렉토리의 내용을 확인했더니 다음과 같이 출력되었다. 현재 디렉토리(.)의 하드 링크 값이 2인 이유를 설명하시오.

```shell
[root@linux1 ch2]# ls -al temp
합계 0
drwxr-xr-x. 2 root root   6  9월 14 13:01 .
drwxr-xr-x. 3 root root 143  9월 14 13:01 ..
[root@linux1 ch2]#
```
같은 파일에 이름이 두 개 있다는 것으로 temp와 현재 디렉터리 두 개가 하드 링크 되었음을 의미 한다.

12. 심볼릭 링크 A의 원본 파일인 B를 삭제한 후 C 파일을 B로 복사했다. 심볼릭 링크 A의 내용을 출력했을 때 어느 파일의 내용이 출력되는가? 왜 그런지 설명하시오.

C 파일의 내용이 출력된다.

```shell
[root@linux1 ch2]# ln -s b a
[root@linux1 ch2]# cat a
Hello World
[root@linux1 ch2]# ls -al
합계 696
drwxr-xr-x. 3 root root    161  9월 14 13:33 .
drwxr-xr-x. 3 root root     17  9월  6 16:39 ..
lrwxrwxrwx. 1 root root      1  9월 14 13:33 a -> b
-rw-r--r--. 1 root root     12  9월 14 13:31 b
-rw-r--r--. 1 root root 692252  9월 13 17:32 data
-rw-r--r--. 1 root root      0  9월 13 20:48 data1
-rw-r--r--. 1 root root      0  9월 12 21:02 data1.ln
lrwxrwxrwx. 1 root root      5  9월 13 12:28 data1.sl -> data1
drwxr-xr-x. 2 root root      6  9월 14 13:01 temp
-rw-r--r--. 2 root root     12  9월 14 12:36 test
-rw-r--r--. 1 root root     12  9월 14 12:43 test_cpopy
-rw-r--r--. 2 root root     12  9월 14 12:36 test_hard
lrwxrwxrwx. 1 root root      4  9월 14 12:41 test_symbolic -> test
[root@linux1 ch2]# rm b
rm: remove 일반 파일 'b'? y
[root@linux1 ch2]# cat a
cat: a: 그런 파일이나 디렉터리가 없습니다
[root@linux1 ch2]# ls -al
합계 692
drwxr-xr-x. 3 root root    152  9월 14 13:33 .
drwxr-xr-x. 3 root root     17  9월  6 16:39 ..
lrwxrwxrwx. 1 root root      1  9월 14 13:33 a -> b
-rw-r--r--. 1 root root 692252  9월 13 17:32 data
-rw-r--r--. 1 root root      0  9월 13 20:48 data1
-rw-r--r--. 1 root root      0  9월 12 21:02 data1.ln
lrwxrwxrwx. 1 root root      5  9월 13 12:28 data1.sl -> data1
drwxr-xr-x. 2 root root      6  9월 14 13:01 temp
-rw-r--r--. 2 root root     12  9월 14 12:36 test
-rw-r--r--. 1 root root     12  9월 14 12:43 test_cpopy
-rw-r--r--. 2 root root     12  9월 14 12:36 test_hard
lrwxrwxrwx. 1 root root      4  9월 14 12:41 test_symbolic -> test
[root@linux1 ch2]# cat a
Hello Wolrd 2
[root@linux1 ch2]# ls -al
합계 700
drwxr-xr-x. 3 root root    170  9월 14 13:35 .
drwxr-xr-x. 3 root root     17  9월  6 16:39 ..
lrwxrwxrwx. 1 root root      1  9월 14 13:33 a -> b
-rw-r--r--. 1 root root     14  9월 14 13:35 b
-rw-r--r--. 1 root root     14  9월 14 13:34 c
-rw-r--r--. 1 root root 692252  9월 13 17:32 data
-rw-r--r--. 1 root root      0  9월 13 20:48 data1
-rw-r--r--. 1 root root      0  9월 12 21:02 data1.ln
lrwxrwxrwx. 1 root root      5  9월 13 12:28 data1.sl -> data1
drwxr-xr-x. 2 root root      6  9월 14 13:01 temp
-rw-r--r--. 2 root root     12  9월 14 12:36 test
-rw-r--r--. 1 root root     12  9월 14 12:43 test_cpopy
-rw-r--r--. 2 root root     12  9월 14 12:36 test_hard
lrwxrwxrwx. 1 root root      4  9월 14 12:41 test_symbolic -> test
[root@linux1 ch2]# [root@linux1 ch2]#
```

13. cp a.txt b.txt c.txt temp는 무엇을 실행하는 명령인가? 여기서 temp는 무엇이어야 하는가?

a.txt, b.txt, c.txt 파일을 temp로 복사한다. temp는 디렉토리이다.

```shell
[root@linux1 ch2]# touch a.txt
[root@linux1 ch2]# touch b.txt
[root@linux1 ch2]# touch c.txt
[root@linux1 ch2]# 
[root@linux1 ch2]# 
[root@linux1 ch2]# 
[root@linux1 ch2]# 
[root@linux1 ch2]# 
[root@linux1 ch2]# cp a.txt b.txt c.txt temp
[root@linux1 ch2]# tree temp
temp
├── a.txt
├── b.txt
└── c.txt

0 directories, 3 files
[root@linux1 ch2]# 
```

14. inode에 대해 간단히 설명하시오.

정규 파일, 디렉터리 등 파일 시스템에 관한 정보를 가지고 있다.
https://ko.wikipedia.org/wiki/%EC%95%84%EC%9D%B4%EB%85%B8%EB%93%9C

```shell
[root@linux1 ch2]# ls -i
18111948 a      18111956 b.txt  18111958 data      18111957 data1.sl  18111960 test_cpopy
18111951 a.txt  18111947 c      18111959 data1     18111939 temp      18124020 test_hard
18111949 b      18111961 c.txt  18124025 data1.ln  18124020 test      18111955 test_symbolic
[root@linux1 ch2]# 
```

```shell
[root@linux1 ch2]# ls -li
합계 688
18111948 lrwxrwxrwx. 1 root root      1  9월 14 13:33 a -> b
18111951 -rw-r--r--. 1 root root      0  9월 14 13:50 a.txt
18111949 -rw-r--r--. 1 root root      0  9월 14 13:36 b
18111956 -rw-r--r--. 1 root root      0  9월 14 13:50 b.txt
18111947 -rw-r--r--. 1 root root     14  9월 14 13:34 c
18111961 -rw-r--r--. 1 root root      0  9월 14 13:50 c.txt
18111958 -rw-r--r--. 1 root root 692252  9월 13 17:32 data
18111959 -rw-r--r--. 1 root root      0  9월 14 13:36 data1
18124025 -rw-r--r--. 1 root root      0  9월 12 21:02 data1.ln
18111957 lrwxrwxrwx. 1 root root      5  9월 13 12:28 data1.sl -> data1
18111939 drwxr-xr-x. 2 root root     45  9월 14 13:50 temp
18124020 -rw-r--r--. 2 root root      0  9월 14 13:36 test
18111960 -rw-r--r--. 1 root root     12  9월 14 12:43 test_cpopy
18124020 -rw-r--r--. 2 root root      0  9월 14 13:36 test_hard
18111955 lrwxrwxrwx. 1 root root      4  9월 14 12:41 test_symbolic -> test
[root@linux1 ch2]# 
```

15. 파일명은 다른데 inode가 같다는 것은 무엇을 의미하는가?

하드링크로 생성 하면 inode 값이 같다. 결론은 같은 파일을 의미한다.

```shell
[root@linux1 ch2]# ln test.txt test_hard.txt
[root@linux1 ch2]# ls -li
합계 688
18111965 -rw-r--r--. 2 root root      0  9월 14 13:56 test.txt
18111965 -rw-r--r--. 2 root root      0  9월 14 13:56 test_hard.txt
[root@linux1 ch2]#
```

---

### 16 ~ 21번 문제 같은 조건

16. 현재 디렉토리가 ch2일 때 다음 표의 빈칸을 채우시오.

```shell
/
├── bin
├── etc
│     └── hosts
├── usr
│     ├── bin
│     └── lib
├── home
│   └── user1
│       ├── ch2
│       │   └── test
│       └── ch3
│           └── data1
└── tmp
```

```shell
[root@linux1 ch2]# pwd
/home/user1/ch2
[root@linux1 ch2]#
```

|파일|절대 경로명|상대 경로명
|---|---|---|
|/|/|../../../|
|lib|/usr/lib|../../../usr/lib|
|data1|/home/user1/ch3/data1|../ch3/data1|
|test|test(/home/user1/ch2/test)|test(../ch2/test)|
|hosts|/etc/hosts|../../../etc/hosts|

```shell
[root@linux1 ch2]# cd /
[root@linux1 /]# pwd
/
```

```shell
[root@linux1 ch2]# cd ../../../
[root@linux1 /]# pwd
/
[root@linux1 /]# 
```

```shell
[root@linux1 ch2]# cd /usr/lib
[root@linux1 lib]# pwd
/usr/lib
[root@linux1 lib]#
```

```shell
[root@linux1 ch2]# cd ../../../usr/lib
[root@linux1 lib]# pwd
/usr/lib
[root@linux1 lib]#
```

```shell
[root@linux1 ch2]# cat /home/user1/ch3/data1
data1 sample
[root@linux1 ch2]# 
```

```shell
[root@linux1 ch2]# cat ../ch3/data1
data1 sample
[root@linux1 ch2]#
```

```shell
[root@linux1 ch2]# cat test
test sample
[root@linux1 ch2]# 
```

```shell
[root@linux1 ch3]# cat /etc/hosts
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6
172.25.3.11	www.example.com
[root@linux1 ch3]# 
```

```shell
[root@linux1 ch2]# cat ../../../etc/hosts
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6
172.25.3.11	www.example.com
[root@linux1 ch2]# 
```

17. 현재 디렉토리를 lib 디렉토리로 이동하는 명령은 무엇인가?

lib 디렉토리 : Library의 약자로, 각종 라이브러리가 저장되어있다. 라이브러리는 프로그래밍에서 함수같은 것이며, 커널 모듈도 이 곳에 위치한다.

```shell
[root@linux1 ch2]# cd /usr/lib
[root@linux1 lib]# pwd
/usr/lib
[root@linux1 lib]# 
```

18. rmdir 명령으로 ch2 디렉토리를 삭제하려고 한다. 삭제되는지 확인하고, 삭제되지 않으면 그 이유를 설명하시오.

ch2 디렉토리에 test 라는 파일이 존재하여 삭제가 되지 않는다. rmdir은 비어있는 디렉토리만 삭제가 가능한 명령어이다.

```shell
[root@linux1 user1]# rmdir ch2
rmdir: failed to remove 'ch2': 디렉터리가 비어있지 않음
[root@linux1 user1]# 
```

19. pwd 명령을실행하니 현재 위치가 /home/user1/ch2였다. data1 파일의 내용을 행 번호를 붙여서 출력하는 명령은 무엇인가?
```shell
[root@linux1 ch2]# cat -n ../ch3/data1
     1	data1 sample
[root@linux1 ch2]# 
```

20. 현재 디렉토리에 data1 파일의 하드 링크를 data1-hard라는 이름으로 만드는 명령은 무엇인가?
```shell
[root@linux1 ch3]# ln data1 data1-hard
[root@linux1 ch3]# ls -li
합계 8
50996282 -rw-r--r--. 2 root root 13  9월 14 14:54 data1
50996282 -rw-r--r--. 2 root root 13  9월 14 14:54 data1-hard
[root@linux1 ch3]#
```

21. 현재 디렉토리에 ch2 디렉토리의 심볼릭 링크를 ch2-sym이라는 이름으로 만드는 명령은 무엇인가?
```shell
[root@linux1 ch3]# ln -s ch2 ch2-sym
[root@linux1 ch3]# ls -li
합계 8
50996283 lrwxrwxrwx. 1 root root  3  9월 14 15:14 ch2-sym -> ch2
50996282 -rw-r--r--. 2 root root 13  9월 14 14:54 data1
50996282 -rw-r--r--. 2 root root 13  9월 14 14:54 data1-hard
[root@linux1 ch3]# 
```

---

22. /etc/passwd 파일에서 문자열 'bash'가 들어 있는 행을 출력하시오.
```shell
[root@linux1 ~]# grep bash /etc/passwd
root:x:0:0:root:/root:/bin/bash
student:x:1000:1000:student:/home/student:/bin/bash
user1:x:1001:1001::/home/user1:/bin/bash
user2:x:1002:1002::/home/user2:/bin/bash
[root@linux1 ~]# 
```

23. /etc 다렉토리 아래에 있는 passwd 파일의 경로를 찾으시오.
```shell
[root@linux1 ~]# find /etc -name passwd
/etc/pam.d/passwd
/etc/passwd
[root@linux1 ~]# 
```

24. cp의 실행 파일이 있는 위치를 검색하시오.
```shell
[root@linux1 ~]# which cp
alias cp='cp -i'
	/usr/bin/cp
[root@linux1 ~]#
```