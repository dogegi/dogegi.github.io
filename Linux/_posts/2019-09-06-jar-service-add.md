---
title: "Linux Jar Service 등록"
categories: Linux
---

출처: http://blog.naver.com/PostView.nhn?blogId=kkwangeun&logNo=220975836994&categoryNo=0&parentCategoryNo=0&viewDate=&currentPage=1&postListTopCurrentPage=1&from=postView

- jar 실행 myapp-start.sh
#!/bin/bash
 java -jar myapp.jar 

- jar 실행 종료 myapp-stop.sh
#!/bin/bash 
# Grabs and kill a process from the pidlist that has the word myapp 

pid=`ps aux | grep myapp | awk '{print $2}'` 
kill -9 $pid

// print $2 ==> pid만 나오게 한다.
root     158511  0.0  0.0      0     0 pts/0    Z    07:26   0:00 java


- 서비스  testService  파일
#!/bin/bash 
# MyApp 
# 
# description: bla bla 
case $1 in
    start) 
        /bin/bash /usr/local/bin/myapp-start.sh
    ;; 
    stop)
        /bin/bash /usr/local/bin/myapp-stop.sh 
    ;; 
    restart)
        /bin/bash /usr/local/bin/myapp-stop.sh 
        /bin/bash /usr/local/bin/myapp-start.sh 
    ;; 
esac 
exit 0

////////////////////////////////

$>/ect/init.d/myscript

1.service 작성
$>cd /etc/init.d/
$>vi myscript
//윙 myscript작성한다.

// 권한을 준다.
$>chmod 755 myscript  
$>chwon root.root myscript

// 실행 
$>service myscript start

//종료
$>service myscirpt stop
