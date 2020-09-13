* 하드 링크(hard link) 생성
  * 기존 파일에 새로운 파일명을 추가로 생성
  * https://ko.wikipedia.org/wiki/%ED%95%98%EB%93%9C_%EB%A7%81%ED%81%AC

```shell
[root@linux1 ch2]# ls -l
합계 4
-rw-r--r--. 1 root root   0  9월 12 21:02 data1
drwxr-xr-x. 2 root root  74  9월 12 21:08 temp
-rw-r--r--. 1 root root 186  9월 12 21:16 test.org
[root@linux1 ch2]# ln data1 data1.ln
[root@linux1 ch2]# ls -l
합계 4
-rw-r--r--. 2 root root   0  9월 12 21:02 data1
-rw-r--r--. 2 root root   0  9월 12 21:02 data1.ln
drwxr-xr-x. 2 root root  74  9월 12 21:08 temp
-rw-r--r--. 1 root root 186  9월 12 21:16 test.org
[root@linux1 ch2]# 
```

```shell
[root@linux1 ch2]# ls -i
18124025 data1  18124025 data1.ln  18111947 temp  18124031 test.org
[root@linux1 ch2]#
```

```shell
[root@linux1 ch2]# cp data1 data1.cp
[root@linux1 ch2]# ls -i
18124025 data1  18111956 data1.cp  18124025 data1.ln  18111947 temp  18124031 test.org
[root@linux1 ch2]# 
```

---

* 심볼릭 링크(symbolic link)
  * 윈도우의 바로가기 기능과 개념이 동일
  * https://ko.wikipedia.org/wiki/%EC%8B%AC%EB%B3%BC%EB%A6%AD_%EB%A7%81%ED%81%AC

```shell
[root@linux1 ch2]# ln -s data1 data1.sl
[root@linux1 ch2]# ls -i
18124025 data1  18111956 data1.cp  18124025 data1.ln  18111957 data1.sl  18111947 temp  18124031 test.org
[root@linux1 ch2]# 
```

```shell
[root@linux1 ch2]# ls -l data1.sl
lrwxrwxrwx. 1 root root 5  9월 13 12:28 data1.sl -> data1
[root@linux1 ch2]# 
```