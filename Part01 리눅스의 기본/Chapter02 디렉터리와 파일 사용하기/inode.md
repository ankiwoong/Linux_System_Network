* inode
  * 파일 = 파일명 + inode + 데이터 블록
    * inode
      * 파일에 대한 정보
      * 번호로 표시
      * 파일의 종류와 크기, 소유자, 파일, 변경 시간, 파일명 등 상세정보
      * 데이터 블록 주소
    * https://ko.wikipedia.org/wiki/%EC%95%84%EC%9D%B4%EB%85%B8%EB%93%9C 

```shell
[root@linux1 ~]# ls -i
33730051 abc.txt          33730052 f1              33730080 file1                  1520947 linux_ex   33730055 test1.txt  18124030 user1      1521484 문서      33579225 사진
34553966 anaconda-ks.cfg  33579255 file-16-16.txt  33730066 file2                 33579261 list0.txt  50996258 tmp1       51620828 공개       1521476 바탕화면  33579215 서식
33579262 err1.txt         33730053 file-16-18.txt  33730077 initial-setup-ks.cfg  33730105 temp        1521532 tmp2       18123975 다운로드  51620829 비디오    18123976 음악
[root@linux1 ~]# 
```