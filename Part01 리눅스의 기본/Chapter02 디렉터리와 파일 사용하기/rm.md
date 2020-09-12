* rm(remove)
* 파일 삭제 / 디렉토리 삭제(-r)

---

* 리눅스는 휴지통에 담기지 않으므로 복구가 불가능하다

```shell
[root@linux1 ch2]# ls
data2  me  one  temp
[root@linux1 ch2]# rm data2
rm: remove 일반 빈 파일 'data2'? y
[root@linux1 ch2]# ls
me  one  temp
[root@linux1 ch2]# 
```

---

-i 옵션
* 삭제 여부 확인

```shell
[root@linux1 ch2]# rm -i data1
rm: remove 일반 빈 파일 'data1'? n
[root@linux1 ch2]# ls
data1  me  one  temp
[root@linux1 ch2]# 
```

---

디렉토리 삭제

```shell
[root@linux1 ch2]# cd temp
[root@linux1 temp]# ls
data2  hosts  services  temp3  text1  text2
[root@linux1 temp]# rm temp3
rm: cannot remove 'temp3': 디렉터리입니다
[root@linux1 temp]# 
```

```shell
[root@linux1 temp]# ls
data2  hosts  services  temp3  text1  text2
[root@linux1 temp]# rm -r temp3
rm: descend into directory 'temp3'? y
rm: remove 일반 파일 'temp3/text1'? y
rm: remove 일반 파일 'temp3/text2'? y
rm: remove 일반 파일 'temp3/hosts'? y
rm: remove 일반 파일 'temp3/services'? y
rm: descend into directory 'temp3/temp'? y
rm: remove 일반 파일 'temp3/temp/text1'? y
rm: remove 일반 파일 'temp3/temp/text2'? y
rm: remove 일반 파일 'temp3/temp/hosts'? y
rm: remove 일반 파일 'temp3/temp/services'? y
rm: remove 디렉토리 'temp3/temp'? y
rm: remove 디렉토리 'temp3'? y
[root@linux1 temp]# ls
data2  hosts  services  text1  text2
[root@linux1 temp]# 
```

```shell
[root@linux1 temp]# ll
합계 696
-rw-r--r--. 1 root root    186  9월  6 19:50 data2
-rw-r--r--. 1 root root    186  9월  6 20:02 hosts
-rw-r--r--. 1 root root 692252  9월  6 20:02 services
drwxr-xr-x. 3 root root     19  9월 12 21:07 test
-rw-r--r--. 1 root root    186  9월  6 19:54 text1
-rw-r--r--. 1 root root    186  9월  6 19:58 text2
[root@linux1 temp]# tree test
test
└── test2
    ├── test
    └── test3

2 directories, 1 file
[root@linux1 temp]# rm -rvf test
removed directory 'test/test2/test3'
removed 'test/test2/test'
removed directory 'test/test2'
removed directory 'test'
[root@linux1 temp]# ll
합계 696
-rw-r--r--. 1 root root    186  9월  6 19:50 data2
-rw-r--r--. 1 root root    186  9월  6 20:02 hosts
-rw-r--r--. 1 root root 692252  9월  6 20:02 services
-rw-r--r--. 1 root root    186  9월  6 19:54 text1
-rw-r--r--. 1 root root    186  9월  6 19:58 text2
[root@linux1 temp]# 
```