* 지정한 경로에서 명령의 바이너리 파일이나 메뉴얼 파일의 위치 검색
* alias 또는 PATH 환경 변수로 지정된 경로에서 검색

```shell
[root@linux1 ch2]# echo $PATH
/usr/local/bin:/usr/local/sbin:/usr/bin:/usr/sbin:/root/bin
[root@linux1 ch2]# 
```

```shell
[root@linux1 ch2]# echo $MANPATH

[root@linux1 ch2]# 
```

```shell
[root@linux1 ch2]# whereis mv
mv: /usr/bin/mv /usr/share/man/man1/mv.1.gz /usr/share/man/man1p/mv.1p.gz
[root@linux1 ch2]#
```