* mv(move)
* 파일 이동하거나 이름 변경

---

* 파일을 파일로 이동하기(파일명 바꾸기)

```shell
[root@linux1 ch2]# mv text1 data1
[root@linux1 ch2]# ls
data1  me  one  temp  temp2
[root@linux1 ch2]# 
```

---

* 파일을 다른 디렉토리로 이동

```shell
[root@linux1 ch2]# mv data1 temp
[root@linux1 ch2]# ls
me  one  temp  temp2
[root@linux1 ch2]# ls temp
data1  hosts  services  text1  text2
[root@linux1 ch2]# 
```

```shell
[root@linux1 ch2]# cp temp/data1 text1
[root@linux1 ch2]# ls
me  one  temp  temp2  text1
[root@linux1 ch2]# mv text1 temp/data2
[root@linux1 ch2]# ls temp
data1  data2  hosts  services  text1  text2
[root@linux1 ch2]#
```

---

* 여러 파일을 디렉토리로 이동

```shell
[root@linux1 ch2]# ls temp
data1  hosts  services  text1  text2
[root@linux1 ch2]# mv temp/data1 temp/data2
[root@linux1 ch2]# ls
me  one  temp  temp2
[root@linux1 ch2]# ls temp
data2  hosts  services  text1  text2
[root@linux1 ch2]# 
```

---

* -i 옵션 사용

```shell
[root@linux1 temp]# mv -i text1 text2
mv: overwrite 'text2'? n
[root@linux1 temp]# ls
data2  hosts  services  text1  text2
[root@linux1 temp]# 
```

---

* 디렉토리를 디렉토리로 이동(디렉토리명 바꾸기)

```shell
[root@linux1 ch2]# mv temp2 temp3
[root@linux1 ch2]# ls
me  one  temp  temp3
[root@linux1 ch2]# 
```

```shell
[root@linux1 ch2]# ls
me  one  temp  temp3
[root@linux1 ch2]# mv temp3 temp
[root@linux1 ch2]# ls
me  one  temp
[root@linux1 ch2]# ls temp
data2  hosts  services  temp3  text1  text2
[root@linux1 ch2]# 
```