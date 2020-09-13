* 빈 파일 생성
* 마지막 접근 시간 또는 수정 시간 변경

```shell
[root@linux1 ch2]# touch test
[root@linux1 ch2]# ls -l test
-rw-r--r--. 1 root root 0  9월 13 17:23 test
[root@linux1 ch2]# 
```

```shell
[root@linux1 ch2]# ls -l data1.cp
-rw-r--r--. 1 root root 0  9월 13 12:19 data1.cp
[root@linux1 ch2]# date
2020. 09. 13. (일) 17:24:30 KST
[root@linux1 ch2]# touch data1.cp
[root@linux1 ch2]# ls -l data1.cp
-rw-r--r--. 1 root root 0  9월 13 17:24 data1.cp
[root@linux1 ch2]# 
```

---

-t

* 변경할 시간을 지정

|형식|설명|
|---|---|
|CC|연도의 첫 두자리|
|YY|연도의 마지막 두 자리|
|MM|달(0 ~ 12)|
|DD|날짜(1 ~ 31)|
|hh|시간(0 ~ 23)|
|mm|분(00 ~ 59)|
|ss|초(00 ~ 59)|

```shell
[root@linux1 ch2]# ls -l test
-rw-r--r--. 1 root root 0  9월 13 17:23 test
[root@linux1 ch2]# touch -t 12311200 test
[root@linux1 ch2]# ls -l test
-rw-r--r--. 1 root root 0 12월 31  2020 test
[root@linux1 ch2]# 
```