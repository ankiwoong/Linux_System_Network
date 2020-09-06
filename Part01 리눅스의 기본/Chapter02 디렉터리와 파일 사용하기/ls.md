* ls(list)
* 디렉토리의 내용 출력

---

* 현재 디렉토리의 내용 확인

```shell
[root@linux1 ~]# ls
abc.txt          err1.txt  file-16-16.txt  file1  initial-setup-ks.cfg  test1.txt  공개      문서      비디오  서식
anaconda-ks.cfg  f1        file-16-18.txt  file2  list0.txt             user1      다운로드  바탕화면  사진    음악
[root@linux1 ~]#
```

---

* 숨김 파일 확인

|기호|종류|
|------|---|
|.|숨김 파일|

```shell
[root@linux1 ~]# ls -a
.              .bash_history  .bashrc  .cshrc     .local  .tcshrc   anaconda-ks.cfg  file-16-16.txt  file2                 test1.txt  다운로드  비디오  음악
..             .bash_logout   .cache   .dbus      .pki    .viminfo  err1.txt         file-16-18.txt  initial-setup-ks.cfg  user1      문서      사진
.ICEauthority  .bash_profile  .config  .esd_auth  .ssh    abc.txt   f1               file1           list0.txt             공개       바탕화면  서식
[root@linux1 ~]#
```

---

* 파일 종류 표시

|기호|종류|
|------|---|
|/|디렉토리|
|@|심볼릭 링크|
||일반 파일|
|*|실행 파일|

```shell
[root@linux1 ~]# ls -F
abc.txt          err1.txt  file-16-16.txt  file1  initial-setup-ks.cfg  test1.txt  공개/      문서/      비디오/  서식/
anaconda-ks.cfg  f1        file-16-18.txt  file2  list0.txt             user1/     다운로드/  바탕화면/  사진/    음악/
[root@linux1 ~]# 
```

```shell
[root@linux1 ~]# ls -aF
./             .bash_history  .bashrc   .cshrc     .local/  .tcshrc   anaconda-ks.cfg  file-16-16.txt  file2                 test1.txt  다운로드/  비디오/  음악/
../            .bash_logout   .cache/   .dbus/     .pki/    .viminfo  err1.txt         file-16-18.txt  initial-setup-ks.cfg  user1/     문서/      사진/
.ICEauthority  .bash_profile  .config/  .esd_auth  .ssh/    abc.txt   f1               file1           list0.txt             공개/      바탕화면/  서식/
[root@linux1 ~]# 
```

---

* 지정한 데렉토리 내용 출력

```shell
[root@linux1 ~]# ls /tmp
systemd-private-bb0f235ab2a84c1fb89643e154abd01d-ModemManager.service-eELZxY  systemd-private-bb0f235ab2a84c1fb89643e154abd01d-fwupd.service-ami8Ib         vmware-root_929-3980167385
systemd-private-bb0f235ab2a84c1fb89643e154abd01d-bluetooth.service-AWlUbM     systemd-private-bb0f235ab2a84c1fb89643e154abd01d-rtkit-daemon.service-Nggb5b  vmware-root_930-2722763397
systemd-private-bb0f235ab2a84c1fb89643e154abd01d-bolt.service-ipjhrd          tracker-extract-files.0                                                       vmware-root_936-2697532681
systemd-private-bb0f235ab2a84c1fb89643e154abd01d-chronyd.service-tMmCBA       vmware-root_910-2697139510                                                    vmware-root_944-2697139479
systemd-private-bb0f235ab2a84c1fb89643e154abd01d-colord.service-yzQrvM        vmware-root_926-2731217702
[root@linux1 ~]# 
```

```shell
[root@linux1 ~]# ls -F /tmp
systemd-private-bb0f235ab2a84c1fb89643e154abd01d-ModemManager.service-eELZxY/  systemd-private-bb0f235ab2a84c1fb89643e154abd01d-fwupd.service-ami8Ib/         vmware-root_929-3980167385/
systemd-private-bb0f235ab2a84c1fb89643e154abd01d-bluetooth.service-AWlUbM/     systemd-private-bb0f235ab2a84c1fb89643e154abd01d-rtkit-daemon.service-Nggb5b/  vmware-root_930-2722763397/
systemd-private-bb0f235ab2a84c1fb89643e154abd01d-bolt.service-ipjhrd/          tracker-extract-files.0/                                                       vmware-root_936-2697532681/
systemd-private-bb0f235ab2a84c1fb89643e154abd01d-chronyd.service-tMmCBA/       vmware-root_910-2697139510/                                                    vmware-root_944-2697139479/
systemd-private-bb0f235ab2a84c1fb89643e154abd01d-colord.service-yzQrvM/        vmware-root_926-2731217702/
[root@linux1 ~]# 
```

---

* 상세 정보 출력

```shell
[root@linux1 ~]# ls -l
합계 36
-rw-r--r--. 1 root root   24  8월 22 18:13 abc.txt
-rw-------. 1 root root 1386  8월 22 15:24 anaconda-ks.cfg
-rw-r--r--. 1 root root   65  8월 22 17:44 err1.txt
-rw-r--r--. 1 root root   20  8월 22 15:53 f1
-rw-r--r--. 1 root root    0  8월 22 16:16 file-16-16.txt
-rw-r--r--. 1 root root    0  8월 22 16:18 file-16-18.txt
-rw-r--r--. 1 root root   13  8월 31 11:09 file1
-rw-r--r--. 1 root root   32  8월 31 11:09 file2
-rw-r--r--. 1 root root 1496  8월 22 15:27 initial-setup-ks.cfg
-rw-r--r--. 1 root root  777  8월 22 17:43 list0.txt
-rw-r--r--. 1 root root   43  8월 22 17:50 test1.txt
drwxr-xr-x. 2 root root    6  9월  5 13:16 user1
drwxr-xr-x. 2 root root    6  8월 22 15:28 공개
drwxr-xr-x. 2 root root    6  8월 22 15:28 다운로드
drwxr-xr-x. 2 root root    6  8월 22 15:28 문서
drwxr-xr-x. 2 root root    6  8월 22 15:28 바탕화면
drwxr-xr-x. 2 root root    6  8월 22 15:28 비디오
drwxr-xr-x. 2 root root  141  8월 31 11:54 사진
drwxr-xr-x. 2 root root    6  8월 22 15:28 서식
drwxr-xr-x. 2 root root    6  8월 22 15:28 음악
[root@linux1 ~]#
```

|필드 번호|필드 값|의미|
|---|---|---|
|1|d|파일 종류|
|2|rwxr-xr-x|파일 접근 권한|
|3|2|하드 링크 개수|
|4|root|파일 소유자|
|5|root|파일이 속한 그룹|
|6|6|파일 크기(바이트)|
|7|8월 22 18:13|파일 마지막 수정 날짜|
|8|공개|파일명|

|문자|파일 유형|
|---|---|
|-|-일반 파일|
|d|디렉토리 파일|
|l|심볼릭 링크 파일|
|b|블록 단위로 읽고 쓰는 블록 장치 파일|
|c|섹터 단위로 읽고 쓰는 문자 장치 파일|
|p|파이프 파일|
|s|소켓|

---

* 디렉토리 자체 정보 확인

```shell
[root@linux1 ~]# ls -ld
dr-xr-x---. 17 root root 4096  9월  6 12:33 .
[root@linux1 ~]#
```

---

* 파일 존재 확인

```shell
[root@linux1 ~]# ls .bash_profile
.bash_profile
[root@linux1 ~]# ls ankiwoong
ls: cannot access 'ankiwoong': 그런 파일이나 디렉터리가 없습니다
[root@linux1 ~]# 
```

---