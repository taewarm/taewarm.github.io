---
title: Fcm Api Test방법
author: TaeWarm
date: 2023-09-25 20:56:00
categories: [FireBase,Fcm]
tags: [writing]
---
# API로 FCM 메세지 보내는법

## 콘솔까지는 미리 다 만들어놓아야함

PostMan 이던지 Talend API Tester 던 API보낼수있는 어떤것을 준비해놓고 다음으로 진행

POST
https://fcm.googleapis.com/fcm/send
Content-Type / application/json
Authorization / 서버 키 //서버키는 firebase console에서 프로젝트설정 -> 클라우드 메시징 -> 서버키를 복사해서 넣어주면됨

<pre>
<code>
{
  "to" : "토큰 값",
  "priority" : "우선순위", //ex) high
  "notification" : {
    "title" : "제목",
    "body" : "내용"
  }
}
// 등등 필요한거 추가해서 body에 넣어서 작업하면됨
</code>
<pre>

전송하면 끝