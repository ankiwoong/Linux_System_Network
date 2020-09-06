* mkdir(make directory)
* 디렉토리 생성

---

* 디렉토리 한 개 생성

```shell
[root@linux1 ~]# mkdir temp
[root@linux1 ~]# ls temp
[root@linux1 ~]# ls
abc.txt          err1.txt  file-16-16.txt  file1  initial-setup-ks.cfg  temp       user1  다운로드  바탕화면  사진  음악
anaconda-ks.cfg  f1        file-16-18.txt  file2  list0.txt             test1.txt  공개   문서      비디오    서식
[root@linux1 ~]#
```

---

* 디렉토리 여러 개 생성


```shell
[root@linux1 ~]# mkdir tmp1 tmp2 tmp3
[root@linux1 ~]# ls
abc.txt          err1.txt  file-16-16.txt  file1  initial-setup-ks.cfg  temp       tmp1  tmp3   공개      문서      비디오  서식
anaconda-ks.cfg  f1        file-16-18.txt  file2  list0.txt             test1.txt  tmp2  user1  다운로드  바탕화면  사진    음악
[root@linux1 ~]#
```

---

* 하위 디렉토리 생성 및 상위 디렉토리 생성

```shell
[root@linux1 ~]# mkdir temp/mid/han
mkdir: `temp/mid/han' 디렉토리를 만들 수 없습니다: 그런 파일이나 디렉터리가 없습니다
[root@linux1 ~]#
```

```shell
[root@linux1 ~]# mkdir -p temp/mid/han
[root@linux1 ~]# ls -R temp
temp:
mid

temp/mid:
han

temp/mid/han:
[root@linux1 ~]# tree temp
temp
└── mid
    └── han

2 directories, 0 files
[root@linux1 ~]# 
```