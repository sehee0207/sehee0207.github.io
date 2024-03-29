---
layout: post
title: Tasting Notes
subtitle : 2학년 2학기 웹프로그래밍 프로젝트 
tags: [Web]
author: Sehee Kim
comments : False
---

<h3> 1. 기간</h3>
2021.11.03 - 2021.12.01

<h3> 2. 프로젝트 명</h3>
Tasting Notes, 와인을 마시고 난 후 감상을 적어놓는 기록을 뜻함

<h3> 3. 설명</h3>
사용자가 자유롭게 자신의 취향이나 일기, 감상을 기록할 수 있는 웹 페이지 (인스타그램 클론 코딩)
<img src="/assets/img/TastingNotes/main.png" width="40%">

<h3> 4. 기술 스택</h3>
<img src="/assets/img/TastingNotes/func.png" width="40%"><br>
<br>좋아요 저장하기 기능<br>
기존의 인스타그램과 동일하게 사용자들이 업로드한 게시물에 최대 1개의 좋아요를 누르거나 저장할 수 있음 게시글은 상단 메뉴의 모아보기에서 한 번에 확인 가능

<h3> 5. 역할</h3>
모든 역할을 수행했다.

<h3> 6. 이슈</h3>
1) <br>
참고하여 개발했던 블로그가 완전히 마무리된 프로젝트가 아니였다는걸 마지막 글에서 깨달았다. 가장 중요한 회원가입 기능이 구현되어 있지 않았고 올해 10월 30일을 마지막으로 블로그는 더이상 올라오지 않았다. 점프 투 장고에서 회원가입을 진행했던 걸 떠올린 뒤에 참고하면서 코드를 뜯어고치기 시작했고 새로고침을 할 때마다 새로운 에러가 등장하는 귀한 경험을 하였다. 1시간 넘게 urls.py 파일만 들여다보다가 models.py 파일에서 필요 없는 줄 알고 삭제했었던 코드 한 줄이 문제가 되어서 작동하지 않은 것을 발견했고 다시 복구 시킨 뒤 무사히 기능 구현에 성공했다! <br><br>

2) <br>
처음에는 댓글 기능을 디스커스를 이용해 구현하였는데 인스타그램의 포인트라고 이야기할 수 있는 댓글 등록이 정상 작동 하지 않음을 발견하였다. 디스커스와 장고를 함께 사용하여 프로젝트를 진행하는 글은 찾기가 어려웠고 또 다시 점프투 장고를 참고하여 코드를 뜯어고쳤다. 어김없이 새로고침을 할 때 마다 새로운 에러가 발생했고 찾아낸 문제점은 url 이 꼬였기 때문이었다. <br>

<h3> 7. 느낀점</h3>
에러를 온전히 혼자 해결해야 한다는 점이 유독 부담스럽게 느껴졌다. 유일하게 개인으로 진행하는 프로젝트라서 더 그랬던 것 같다. 결론적으로 많은 에러와 고난을 이겨내고 프로젝트를 무사히 끝낼 수 있어서 기분이 좋았다. 친구들 피드백에는 여러 기능을 더 추가한다면 완성도 높은 프로젝트가 될 것 같다, CSS 에 신경을 많이 쓴 것 같다, 화면이 깔끔하다 등이 있었고 열심히 노력한게 다른 사람들 눈에도 보이는 것 같아서 뿌듯했다. 개발을 하다보면 쉽게 마주칠 수 있는 상황이라 그런지 내가 겪었던 이슈를 듣고 안쓰럽다고 이야기한 친구도 있었다. 3학년 때도 웹을 선택했는데 벗어날 수 없는듯 하다. 점점 전공이 확실하게 정해지고 있다 ... 방학 때 장고를 다시 복습해보는 것도 나쁘지 않을 것 같다. 시간이 있다면!

<h3> 8. 보완하고 싶은 점</h3>
팔로우 기능, 댓글 좋아요 기능 등 여러가지를 더 추가하고 싶다.

<h3> 9. Github</h3>
[Tasting_Notes](https://github.com/sehee0207/Tasting_Notes)