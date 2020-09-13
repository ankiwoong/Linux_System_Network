* 파일 내에서 특정 문자열 검색

---

* 인자로 지정한 문자열 검색

```shell
[root@linux1 ch2]# cp /etc/services data
[root@linux1 ch2]# grep DHCP data
dhcp-failover   647/tcp                 # DHCP Failover
dhcp-failover   647/udp                 # DHCP Failover
[root@linux1 ch2]# 
```

---

* 인저로 지정한 문자열에 행번호도 출력

```shell
[root@linux1 ch2]# grep -n DHCP data
1413:dhcp-failover   647/tcp                 # DHCP Failover
1414:dhcp-failover   647/udp                 # DHCP Failover
[root@linux1 ch2]# 
```