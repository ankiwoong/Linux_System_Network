* cp(copy)
* 파일이나 디렉토리를 복사

```shell
[root@linux1 ~]# cd linux_ex/ch2/
[root@linux1 ch2]# pwd
/root/linux_ex/ch2
[root@linux1 ch2]# 
```

* 두인자가 모두 파일인 경우

```shell
[root@linux1 ch2]# ls
me  one
[root@linux1 ch2]# cp /etc/hosts text1
[root@linux1 ch2]# ls
me  one  text1
[root@linux1 ch2]#
```

```shell
[root@linux1 ch2]# cat text1 
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6
172.25.3.11	www.example.com
[root@linux1 ch2]#
```
---

* 두 번째 인자가 디렉토리인 경우

```shell
[root@linux1 ch2]# mkdir temp
[root@linux1 ch2]# cp text1 temp
[root@linux1 ch2]# ls temp
text1
[root@linux1 ch2]#
```

```shell
[root@linux1 ch2]# cat text1 
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6
172.25.3.11	www.example.com
[root@linux1 ch2]# 
```

```shell
[root@linux1 ch2]# cp text1 temp/text2
[root@linux1 ch2]# ls temp
text1  text2
[root@linux1 ch2]#
```

```shell
[root@linux1 ch2]# cd temp/
[root@linux1 temp]# cat text2
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6
172.25.3.11	www.example.com
[root@linux1 temp]#
```

---

* 인자를 여러 개 지정

```shell
[root@linux1 ch2]# cp /etc/hosts /etc/services temp
[root@linux1 ch2]# ls temp
hosts  services  text1  text2
[root@linux1 ch2]# 
```

---

* -i 옵션 사용

```shell
[root@linux1 ch2]# cp -i /etc/hosts text1
cp: overwrite 'text1'? n
[root@linux1 ch2]#
```

---

* 디렉토리 복사하기

```shell
[root@linux1 ch2]# cp temp temp2
cp: -r not specified; omitting directory 'temp'
[root@linux1 ch2]#
```

```shell
[root@linux1 ch2]# cp -r temp temp2
[root@linux1 ch2]# ls temp2
hosts  services  text1  text2
[root@linux1 ch2]# 
```

```shell
[root@linux1 ch2]# cp -r temp temp2
[root@linux1 ch2]# ls temp2
hosts  services  temp  text1  text2
[root@linux1 ch2]# 
```