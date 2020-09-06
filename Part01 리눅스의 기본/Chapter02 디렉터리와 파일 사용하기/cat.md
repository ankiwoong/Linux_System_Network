* 파일 내용 출력

```shell
[root@linux1 ~]# cat /etc/hosts
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6
172.25.3.11	www.example.com
[root@linux1 ~]#
```

```shell
[root@linux1 ~]# cat -n /etc/hosts
     1	127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
     2	::1         localhost localhost.localdomain localhost6 localhost6.localdomain6
     3	172.25.3.11	www.example.com
[root@linux1 ~]# 
```