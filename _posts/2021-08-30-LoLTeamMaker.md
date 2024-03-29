---
layout: post
title: LoLTeamMaker
subtitle : 라이엇 API를 이용한 롤 내전 팀 분배 웹 사이트
tags: [Web]
author: Sehee Kim
comments : False
---

<h3> 1. 기간</h3>
2021.07.25 - 2021.08.22

<h3> 2. 프로젝트 명</h3>
LoLTeamMaker

<h3> 3. 설명</h3>
League of Legends 게임 내에 최대 10명의 친구들을 모아 5:5 팀 게임을 진행할 수 있는 사용자 설정 게임에서 균형 잡힌 팀 배분을 돕는 웹페이지<br>
[LoLTeamMaker](https://lolteammaker-3fece.web.app/) <br>
<img src="/assets/img/LoLTeamMaker/main.jpg" width="40%">

<h3> 4. 기술 스택</h3>
1) Index.js 41~55 fetch() 를 통해 API 가져오기<br>
fetch의 값으로 들어가는 URL은 두개의 URL로 나누어진다.<br>
1번째 부분은 CORS에러를 방지하기 위해 타인이 만든 프록시 서버를 연결해주기 위한 링크이다. <br>
https://cors-anywhere.herokuapp.com/  <br><br>
2번째 부분은 riotAPI를 가져오기 위한 링크 로서 사용자가 입력한 소환사명과 riotAPI_KEY를 요구한다.<br>
https://kr.api.riotgames.com/lol/summoner/v4/summoners/by-name/${summoner_name}?api_key=${API_KEY}<br>
((여기서 summoner_name은 사용자가 입력한 소환사명을 뜻하고
API_KEY는 riot에게 발급받은 API_KEY를 뜻하는 변수이다.))<br><br>
fetch()함수 뒤에 .then을 통하여 API데이터를 가져오게 된다. <br>
첫번째 API에서 필요한 데이터는 소환사의 id값이기 때문에 data.id를 가져와준다. 동시에 소환사의 티어를 가져오기 위해서 소환사의 id와 소환사명이 둘 다 필요하기 때문에 data.name도 getSummoner_tier()함수에 보내준다.<br>

<hr>

2) Index.js 193~269 팀 섞기<br>
suffleTeam 함수는 말 그대로 팀을 섞는 함수이다. 기본적으로 각각의 소환사들은 티어에 따라 정해진 점수를 받게 된다. 이 점수를 기반으로 Blue 팀과 red 팀이 서로 평균 티어가 비슷하게 팀을 짜게 한다. <br> 기본적으로 무한 루프문 안에서 shuffleArray 함수를 통해 사용자 데이터가 들어있는 score_list 배열을 섞어준다. 이때 0~4번 인덱스의 티어 총합을 teamA에 5~10번 인덱스의 티어 총합을 teamB에 저장한다. <br>후 teamA와 teamB의 차이를 구하고 tiergap과 비교해본다. 이때 tiergap은 기본적으로 5가 주어져 있고 사용자가 변경 가능하다. 이때 양 팀의 티어 차가 tiergap보다 작게되면 무한 루프를 빠져나간다.

<h3> 5. 역할</h3>
전반적인 CSS 및 호스팅

<h3> 6. 이슈</h3>
이름 정하는 데에서 많은 고민을 했다. 직관적으로 뭐 하는 웹페이지인지에 대해 이야기 해줄지, 별명을 붙이거나 이니셜로 나타낼지 고민하다가 그냥 LoLTeamMaker 로 결정했다. API 승인을 받기 위해 라이엇에게 편지도 썼다. ㅋㅋㅋㅋ 그래도 cors 에러가 있어서 서버가 원활하게 돌아가는 거 같지는 않다. 해결할 수 있는 방법이 두 가지 있는데 하나는 포기하는 거고 하나는 라이엇에게 전화해서 우리가 만든 서버를 허용해달라고 부탁하는건데 우리는 첫번째 방법을 선택했다. 사실 해결할 수 있는 방법이 있기는 했지만 프록시 어쩌구저쩌구 글을 보고 이해를 못해서 포기한 것도 있다. 더 많이 배포해서 많은 사람들이 사용할 수 있게 하려면 여러 기능도 추가하고 이런 에러들도 수정해야 할 것 같다.
![letter](/assets/img/LoLTeamMaker/letter.png)
→ 이거 작성하면서 애들이랑 되게 많이 웃었다 ㅋㅋㅋ 솔직히 이런 거까지 할 줄도 몰랐고 승인 받을지도 몰랐는데 막상 받으니까 뿌듯하고 기분도 좋았다. 매일 Riot Developer 들어가서 확인했는데 승인 해주는 데까지 시간도 살짝 걸렸다. 뭔가 인정받은 기분이 들었다. (⸝⸝･ᴗ･⸝⸝)੭˒˒ 부끄럽군.

<h3> 7. 느낀점</h3>
전반적으로 요소들의 순서를 조절하고 기능은 이미 완벽했기 때문에 페이지를 더 예쁘게 만들기 위해서 노력했다. 학과장 선생님이 대학교 가서 1학년 즈음에 시간이 남고 웹 개발자를 생각하고 있다면 UI/UX 와 같은 디자인을 공부하는 것도 괜찮다고 말씀하셨는데 이번 프로젝트를 진행하면서 뼈저리게 느꼈다. 뭔가 더 디자인적인 요소가 추가된다면 훨씬 괜찮은 웹 페이지가 될 것이라고 생각한다. 즐겨했었던 (과거형이다. 지금은 끊었다.) 게임과 관련한 웹 페이지를 만드니까 뭔가 더 신기하고 재미있었다. 한 가지 아쉬운 점은 이 게임에 대해 잘 알지 못하는 사람들은 우리가 개발한 웹 페이지를 어떻게 사용해야 하는지 잘 모를 것 같다. 최대한 자세하게 설명을 하려고 노력했지만 역시 아는걸 설명하는게 제일 어렵다. 

<h3> 8. 보완하고 싶은 점</h3>
1) 자체 밸런스 조절 기능 : 사용자가 랜덤으로 생성된 팀을 보고 보인이 생각하는 더 좋은 팀이 있다면 직접 팀 구성원을 변경할 수 있게 하는 기능<br>

2) 포지션 설정 기능 : 소환사의 모스트 포지션을 기준으로 각각의 유저가 원하는 포지션을 갈 수 있도록 유동적인 팀 생성을 돕는 기능 <br>

3) 인원수 조절 기능 : 사용자 설정 게임을 하는 인원이 10명 미만이더라도 균형 잡힌 팀을 구성해주는 기능 <br>

4) 유저 친화적인 인터페이스 기능 : 사용자가 더 쉽게 웹페이지의 기능을 사용할 수 있도록 변경<br>

<h3> 9. Github</h3>
[LoLTeamMaker](https://github.com/sehee0207/LoLTeamMaker)