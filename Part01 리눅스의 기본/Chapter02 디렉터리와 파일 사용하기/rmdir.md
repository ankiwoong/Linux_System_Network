* rmdir(Remove Directory)
* 디렉토리를 삭제

---

* 디렉토리 삭제

```shell
[root@linux1 ~]# rmdir tmp3
[root@linux1 ~]# ls
abc.txt          err1.txt  file-16-16.txt  file1  initial-setup-ks.cfg  temp       tmp1  user1  다운로드  바탕화면  사진  음악
anaconda-ks.cfg  f1        file-16-18.txt  file2  list0.txt             test1.txt  tmp2  공개   문서      비디오    서식
[root@linux1 ~]# 
```

---

* 비어있지 않은 디렉토리는 삭제가 안됨

```shell
[root@linux1 ~]# rmdir temp
rmdir: failed to remove 'temp': 디렉터리가 비어있지 않음
[root@linux1 ~]# 
```