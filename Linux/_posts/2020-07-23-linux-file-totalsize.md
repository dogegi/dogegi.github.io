---
title: "Linux Jar Service 등록"
categories: Linux
---

# Linux 파일 용량 총합 구하기

```bash
find ./ -type f -name "*.wav" -ls | awk '{ result += $7 } END { print result }'
```
```bash
find ./ -type f -name "*.wav" -ls
```
find 는 경로 및 검색할 파일이름/확장자를 지정하는 것이고, -ls 는 ls 방식으로 출력함을 표기
```bash
 | awk '{ result += $7 } END { print result }'
 ```
PIPE 다음의 awk는 출력값의 7번째 칸을 result 변수에 더하고, 출력
