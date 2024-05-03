---
layout: post
title: 깃허브 블로그 접어야하나 고민하게 한 Paginator
author: 개발자씅
categories: 
- 코딩
tags: 깃허브블로그
date: 2024-05-02 12:00 +0800
lastmode: 2024-05-02 12:00 +0800
sitemap:
  changefreq: daily
  priority : 1.0
published: true
toc: true
excerpt: 깃허브 블로그 디렉토리 정리 및 수정 계획, 엄청 마음고생시킨 Paginator 문제 해결 과정
---
### 메뉴수정사항
──BLOG<br>
  &emsp;├─<span style="color: blue;">[추가] project *main </span><br>
  &emsp;│ : 프로젝트 과정 기록 메뉴, main폴더로 변경<br>
  &emsp;├──<del>about</del> [삭제] : 프로필은 한 페이지로 작성 예정<br>
  &emsp;└──blog <del>*main</del> [삭제] 매일 공부한 개념 정리 및 글쓰기 연습 폴더<br>
  <br>
  > 메뉴를 프로젝트와 블로그 두개로 운영예정이다. <br>
  **프로젝트**는 팀프로젝트와 개인프로젝트의 진행과정을 글로 기록하는 메뉴로 현재 팀에서 진행중인  ERP시스템 제작 중 고객관리 파트를 맡아 진행중인 내용과 개인적으로 일기장 어플을 만드는 과정을 기록하고자 한다. <br>
  **블로그**에는 수업시간에 배운 개념에 대한 심화학습을 중심으로 독서에 관한 성찰이나 다양한 유익한 깨달음을 소재로 글을 꾸준히 써보고자 한다. 1페이지 자기소개는 메뉴에서 빼고 별도로 작성했다.

<br>
### 폴더수정사항
──BLOG<br>
  &emsp;├──_data : 기본설정파일 외 설정파일 모음폴더<br>
  &emsp;├──_includes : 페이지 구성 조각 모음 폴더<br>
  &emsp;├──_layouts<br>
  &emsp;├──_posts : blog에 작성한 글 모음 폴더<br>
  &emsp;├─<span style="color: blue;">[추가] logs : project에 관한 기록 글 모음 폴더</span><br>
  &emsp;├──_sass : 스타일 설정파일 모음폴더<br>
  &emsp;├──_site<br>
  &emsp;├──.sass-cache<br>
  &emsp;├──assets  <br>
  &emsp;└──script<br>
  &emsp;<span style="color: blue;">[추가] blog : blog목록페이지 index.html</span><br>
  &emsp;<span style="color: blue;">[추가] project <br>
    &emsp;&emsp;├──ERP System : 이 프로젝트의 목록페이지 index.html<br>
    &emsp;&emsp;└──Diary Project : 이 프로젝트의 목록페이지 index.html<br> </span>

 > **이부분이 자꾸 헷갈림** <br>
 blog - 전체 포스트 목록 - 날짜/카테고리/태그별 포스트 목록 
            -> 포스트 목록 수정 : 전체/ 카테고리별  
 project - 프로젝트 목록 - 프로젝트1의 로그 목록(블로그의 날짜 형식으로 변경)

### 파일수정사항
──BLOG<br>
  &emsp;├──_data<br>
  &emsp;│&emsp;&emsp;├──archive.yml : <헤더>블로그 분류 메뉴(날짜/카테/태그)<br>
  &emsp;│&emsp;&emsp;├──navigation.yml : <사이드바>블로그 전체 메뉴(프젝/블로그)<br>
  &emsp;│&emsp;&emsp;├──social.yml :<사이드바>소셜(깃허브/유튜브)<br>
  &emsp;│&emsp;&emsp;└─<span style="color: blue;">[추가] project.yml : 프로젝트 목록관련 설정</span><br>
  &emsp;├──_includes<br>
  &emsp;│&emsp;&emsp;├──content.html : 본문 영역과 풋터<br>
  &emsp;│&emsp;&emsp;├──custom-head.html<br>
  &emsp;│&emsp;&emsp;├──disqus.html : 댓글*나중에 꼭 해보자<br>
  &emsp;│&emsp;&emsp;├──google-analytics.html <br>
  &emsp;│&emsp;&emsp;├──head.html<br>
  &emsp;│&emsp;&emsp;├──home-header.html : 목록 분류 메뉴(날짜/카테고리/태그)<br>
  &emsp;│&emsp;&emsp;├──mathjax.html<br>
  &emsp;│&emsp;&emsp;├──post-tags.html : 포스트 태그<br>
  &emsp;│&emsp;&emsp;├──scroll.html<br>
  &emsp;│&emsp;&emsp;├──sidebar-left.html : 왼쪽사이드바(제목/메뉴/소셜)<br>
  &emsp;│&emsp;&emsp;├──sidebar-right.html : 오른쪽사이드바(본문 목차 영역)<br>
  &emsp;│&emsp;&emsp;└──toc.html : 본문 목차<br>
  &emsp;├──_layouts<br>
  &emsp;│&emsp;&emsp;├──archive-dates.html : 본문 시간별 목록<br>
  &emsp;│&emsp;&emsp;├──archive-taxonomies.html 본문: 카테고리/태그별 목록<br>
  &emsp;│&emsp;&emsp;├──default.html <br>
  &emsp;│&emsp;&emsp;├──home.html : 블로그 목록<br>
  &emsp;│&emsp;&emsp;├──page.html<br>
  &emsp;│&emsp;&emsp;└──post.html : 본문<br>
  &emsp;├──_sass<br>
  &emsp;│&emsp;&emsp;├──_alignment.scss<br>
  &emsp;│&emsp;&emsp;├──_archive.scss<br>
  &emsp;│&emsp;&emsp;├──_base.scss<br>
  &emsp;│&emsp;&emsp;├──_code.scss<br>
  &emsp;│&emsp;&emsp;├──_home-header.scss<br>
  &emsp;│&emsp;&emsp;├──_layout.scss<br>
  &emsp;│&emsp;&emsp;├──_message.scss<br>
  &emsp;│&emsp;&emsp;├──_pagination.scss<br>
  &emsp;│&emsp;&emsp;├──_post.scss<br>
  &emsp;│&emsp;&emsp;├──_sidebar.scss<br>
  &emsp;│&emsp;&emsp;├──_syntax-dark.scss<br>
  &emsp;│&emsp;&emsp;├──_syntax-light.scss<br>
  &emsp;│&emsp;&emsp;├──_toc.scss<br>
  &emsp;│&emsp;&emsp;├──_type.scss<br>
  &emsp;│&emsp;&emsp;└──_bariables.scss<br>
  &emsp;├──_site       <br>
  &emsp;├──.sass-cache<br>
  &emsp;├──assets<br>
  &emsp;│&emsp;&emsp;└──styles.scss<br>
  &emsp;├──scripts<br>
  &emsp;├──_config.yml : 기본설정<br>
  &emsp;├──404.html<br>
  &emsp;├──about.html : 프로필 페이지<br>
  &emsp;├──avatar.jpeg : 사이드바 사진<br>
  &emsp;├──bg.jpeg : 사이드바 배경 사진<br>
  &emsp;├──categories.md : 목록 분류 메뉴 카테고리 설정<br>
  &emsp;├──dates.md : 목록 분류 메뉴 날짜 설정<br>
  &emsp;├──Gemfile<br>
  &emsp;├──Gemfile.lock<br>
  &emsp;├──index.html : 메인페이지(project 목록)<br>
  &emsp;├──LICENSE.md<br>
  &emsp;├──README.md<br>
  &emsp;└──tags.md : 목록 분류 메뉴 카테고리 설정<br>
  <br>

### 수정계획
  
  1. <DEL>log랑 project메뉴 연결, log 업로드</DEL>
  2. <DEL>전체 프로젝트 목록 - 개별 프로젝트목록(시간별)</DEL>
  3. <DEL>블로그 목록 <-> 카테고리별 목록, 태그별 목록 삭제</DEL>
  4. 블로그 및 프로젝트 목록 레이아웃, 사진포함
  4. 검색엔진 등록
  5. 프로필 레이아웃 -> 자기개발 계획 연동
  6. 프로젝트/블로그 메뉴 반응성 수정
  7. toc반응성 수정
  8. 소셜수정 카톡도 되나?
  9. 댓글
  10. 검색기능 가능할려나?
  12. <추가>본문에 태그 빼기
  13. <추가>log에 추천글 수정하기, 이전글 다음글 다른 양식으로 넣고 싶다
  14. 사이드바 문구 확정


  일단 이렇게 <DEL>11개</DEL> 14개, 수정을 차근차근 진행해보자. 

  뭔가 굉장히 많이 수정한 것 같아서 파일명까지 기록하여 정리하자고 생각하고 시작했는데 생각보다 많이 수정 안했구나 싶다. 아마 시작부터 헛손가락질이 어마어마해서 굉장히 많은 작업을 했다고 생각했으나 실상은 제자리 걸음이었던 것으로 확인했다. 내가 그제부터 헛손가락질 한 것이 무엇인가 하면. jekyll의 paginator기능이 실행되지 않아서 수정하려고 한 일들 이었다. project메뉴를 만들고 싶어서 추가하고 기본적인 틀은 blog를 활용해야겠다 싶어서 이것저것 복사했다. 그리고 페이지가 이동되도록 각 파일들을 연결했다. 어제그제 두어개 글을 쓰고 나니 잘 나오던 blog목록이 안나오는 것이 문제의 발단이었다. 날짜, 카테고리, 태그별로 보는 목록은 잘 나오는데 전체 포스트 목록만 안나왔다. 뭐가 문제일까. 같은 설정의 파일들이 여러개 만들어진 것이 문제일까? config 파일 설정이 문제일까? 목록 코드가 내가 여기저기 복붙하면서 누락된 부분이 있는지 두 밤을 새도록 얼마나 확인을 했는지.. 그렇게 지피티 선생님과 고군분투하다가 알게된 사실, **jekyll의 paginator는 index.html파일에서만 작동한다는 것**이었다. 목록이 출력이 안나온 결정적인 이유는 내가 메인페이지를 블로그에서 프로젝트로 바꾸면서 **블로그 목록 페이지의 이름이 변경**되었기 때문이었다. 그래도 반가운 소식이 있었다. **Jekyll-paginate-v2 플러그인**을 설치하면 해결된다고 했다. 그 순간 느꼈다. 오, 해결됐다!!! 하지만 나의 반짝였던 기대감은 무너지고 해결되지 않았다. 각 페이지의 설정, 설정파일의 설정, 파일이름, 폴더이름을 늦은 밤까지 들여다봤지만 해결하지 못한 채 찜찜한 아침을 맞았다. 그리고 학원 가는 길, 새벽까지 블로그를 봐서 피곤하고 힘이 쭉 빠져 있었다. 비몽사몽한 중에도 어제의 문제가 떠올랐다. 그리고 핸드폰을 들어 검색했다. **jekyll pagination not working** 많은 사람들이 너도나도 안된다고 글을 올렸고 많은 사람들이 도움을 주고자 답변을 달아놨다. 그러다 눈에 띈 글, "index.html파일에서만 작동해요." "오, 파일명을 변경하고 경로에 폴더명을 추가해서 해결했어요!" "아 그문제는 jekyll공식사이트에도 있어요. Jekyll-paginate-v2로 해결했습니다." 그리고 **"Jekyll-paginate-v2 은 github.io에서는 작동하지 않아요."  하.. 나는 누구인가, 여기는 어디인가, 나는 어디로 가고 있는가, 삶이란 무엇인가.** 안되는 이유가 다 있었다. 오전은 쉬고 오후에 다시 찬찬히 시도해보기로 했다. 사람들도 문제가 있고 물어보고 도와주면서 해결해가고 있었다. 나라고 못 할 이유가 없다. 다시 마음을 잡았다. github블로그에서는 쓸모없는 Jekyll-paginate-v2를 지우고 다시 차근차근 폴더명과 파일명, 경로를 확인하고 Jekyll공식홈페이지에서 안내하는 설정문구를 작성했다. **어라? 되네?!**

  수업시간에 선생님이 **공식사이트**를 계속 찾아주시면서 수업을 한 이유가 다 있었다. 내가 물어보는 즉시 바로바로 답을 내놓는 지피티가 편리해서 자꾸 묻다보니 돌고도는 답변속에서 헤어나오지 못하고 밤을 지새웠지만, **안될 땐 얼른 다시 생각을 정리하고 마음을 가다듬고 다른 방법을 생각해야겠다.**(아니면 잠이라도 자자.) 당연히 코드 문제일꺼라고 생각했다. 폴더명, 파일명이 문제일꺼라고는 생각도 못했다. 뭘 알아야 질문도 하지. 오늘도 하나 배웠다. 개설한지 일주일만에 심각하게 접을까 고민하게한 문제였지만, 가뿐하게ㅋㅋㅋ 잘 해결함으로써 오히려 **할 수 있을 것 같다는 자신감이 불어와 나를 다시 한 번 설레이게 하는 경험이었다.**