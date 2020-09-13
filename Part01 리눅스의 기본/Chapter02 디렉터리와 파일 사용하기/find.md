* 계층 구조에서 특정 파일이 어느 디렉토리에 있는지 검색

```shell
[root@linux1 ch2]# find /usr -name ls
/usr/bin/ls
[root@linux1 ch2]# 
```

---

* 특정 사용자 계정 소유자인 파일 검색

```shell
[root@linux1 ch2]# find /home -user user1
/home/user1
/home/user1/.mozilla
/home/user1/.mozilla/extensions
/home/user1/.mozilla/plugins
/home/user1/.bash_logout
/home/user1/.bash_profile
/home/user1/.bashrc
[root@linux1 ch2]# 
```

---

-exec / -ok

* 검색한 모든 파일을 대상으로 동일한 작업 수행

```shell
[root@linux1 ch2]# find /tmp -user user1 -exec rm {} \;
```

```shell
[root@linux1 ch2]# find /tmp -user user1 -ok rm {} \;
```