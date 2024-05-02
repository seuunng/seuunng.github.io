---
layout: post
title: 깃허브 블로그 수정계획
author: seuunng
categories: 
- 코딩
tags: 깃허브블로그
date: 2024-05-02 12:00 +0800
#last_modified_at: 2024-10-30 22:00 +0800
published: true
toc: true
excerpt: 깃허브 블로그 디렉토리 정리 및 엄청 마음 고생한 페이지네이터 정리
---
### 메뉴수정사항
──BLOG<br>
  │ *추가 project *main : 프로젝트 과정 기록 메뉴, main폴더 변경<br>
  ├──about *삭제 : 프로필은 사진누르면 나오는 1페이지로 작성 예정<br>
  └──blog *main *삭제 : 매일 공부한 개념 정리 및 글쓰기 연습 폴더<br>
  <br>
  > 메뉴를 프로젝트와 블로그 두개로 운영예정이다. <br>
  **프로젝트**는 팀프로젝트와 개인프로젝트의 진행과정을 글로 기록하는 메뉴로 현재 팀에서 진행중인  ERP시스템 제작 중 고객관리 파트를 맡아 진행중인 내용과 개인적으로 일기장 어플을 만드는 과정을 기록하고자 한다. <br>
  **블로그**에는 수업시간에 배운 개념에 대한 심화학습을 중심으로 독서에 관한 성찰이나 다양한 유익한 깨달음을 소재로 글을 꾸준히 써보고자 한다. 1페이지 자기소개는 메뉴에서 빼고 별도로 작성했다.

### 폴더수정사항
──BLOG<br>
  ├──_data<br>
  ├──_includes<br>
  ├──_layouts<br>
  ├──_posts : blog에 작성한 글 모음 폴더<br>
  │   *추가 logs : project에 관한 기록 글 모음 폴더<br>
  ├──_sass<br>
  ├──_site<br>
  ├──.sass-cache<br>
  ├──assets  <br>
  └──script<br>
  *blog : blog목록페이지 index.html
  *project 
    ├──ERP System : 이 프로젝트의 목록페이지 index.html
    └──Diary Project : 이 프로젝트의 목록페이지 index.html

 > **이부분이 자꾸 헷갈림** <br>
 blog - 전체 포스트 목록 - 날짜/카테고리/태그별 포스트 목록 
            -> 카테고리/태그별 포스트 목록으로 수정
 project - 프로젝트 목록 - 프로젝트1의 로그 목록(블로그의 날짜 형식으로 변경)

### 파일수정사항
──BLOG<br>
  ├──_data<br>
  │     ├──archive.yml : <헤더>블로그 분류 메뉴 설정(날짜/카테고리/태그)<br>
  │     ├──navigation.yml : <왼쪽사이드바>블로그 전체 메뉴 설정(프로젝트/블로그)<br>
  │     └──social.yml :<왼쪽사이드바>소셜(깃허브/유튜브)<br>
  │         * 추가 project.yml : 프로젝트 목록관련 설정<br>
  ├──_includes<br>
  │     ├──content.html<br>
  │     ├──custom-head.html<br>
  │     ├──disqus.html<br>
  │     ├──google-analytics.html<br>
  │     ├──head.html<br>
  │     ├──home-header.html<br>
  │     ├──mathjax.html<br>
  │     ├──post-tags.html<br>
  │     ├──scroll.html<br>
  │     ├──sidebar-left.html<br>
  │     ├──sidebar-right.html<br>
  │     └──toc.html<br>
  ├──_layouts<br>
  │     ├──archive-dates.html<br>
  │     ├──archive-taxonomies.html<br>
  │     ├──default.html<br>
  │     ├──home.html<br>
  │     ├──page.html<br>
  │     └──post.html<br>
  ├──_sass<br>
  │     ├──_alignment.scss<br>
  │     ├──_archive.scss<br>
  │     ├──_base.scss<br>
  │     ├──_code.scss<br>
  │     ├──_home-header.scss<br>
  │     ├──_layout.scss<br>
  │     ├──_message.scss<br>
  │     ├──_pagination.scss<br>
  │     ├──_post.scss<br>
  │     ├──_sidebar.scss<br>
  │     ├──_syntax-dark.scss<br>
  │     ├──_syntax-light.scss<br>
  │     ├──_toc.scss<br>
  │     ├──_type.scss<br>
  │     └──_bariables.scss<br>
  ├──_site       <br>
  ├──.sass-cache<br>
  ├──assets<br>
  │     └──styles.scss<br>
  ├──scripts<br>
  ├──_config.yml<br>
  ├──404.html<br>
  ├──about.html<br>
  ├──avatar.jpeg<br>
  ├──bg.jpeg<br>
  ├──categories.md<br>
  ├──dates.md<br>
  ├──Gemfile<br>
  ├──Gemfile.lock<br>
  ├──index.html : 메인페이지(project 목록)<br>
  ├──LICENSE.md<br>
  ├──README.md<br>
  └──tags.md<br>

  뭔가 굉장히 많이 수정한 것 같아서 파일명까지 기록하여 정리하자고 생각하고 시작했는데 생각보다 많이 수정 안했구나 싶다. 아마 시작부터 헛발질이 어마어마해서 굉장히 많은 작업을 했다고 생각했으나 실상은 제자리 걸음이었던 것으로 확인했다. 내가 그제부터 헛발질 한 것이 무엇인가 하면. jekyll의 paginator기능이 실행되지 않아서 수정하려고 한 일들 이었다. project메뉴를 만들고 싶어서 추가하고 기본적인 틀은 blog를 활용해야겠다 싶어서 이것저것 복사했다. 그리고 페이지가 이동되도록 각 파일들을 연결했다. 어제그제 두어개 글을 쓰고 나니 잘 나오던 blog목록이 안나오는 것이 문제의 발단이었다. 날짜, 카테고리, 태그별로 보는 목록은 잘 나오는데 전체 포스트 목록만 안나왔다. 뭐가 문제일까. 같은 설정의 파일들이 여러개 만들어진 것이 문제일까? config 파일 설정이 문제일까? 목록 코드가 내가 여기저기 복붙하면서 누락된 부분이 있는지 두밤을 새도록 얼마나 확인을 했는지.. 덕분에 어떤 폴더에 어떤 파일이 들어있는지는 꽤 파악이 되었다. 그렇게 지피티 선생님과 고군분투하다가 알게된 사실, jekyll의 paginator는 index.html파일에서만 작동한다는 것이었다. 목록이 출력이 안나온 결정적인 이유는 내가 메인페이지를 블로그에서 프로젝트로 바꾸면서 블로그 목록 페이지이 이름이 변경되었기 때문이었다. 그래도 반가운 소식이 있었다. Jekyll-paginate-v2 플러그인을 설치하면 해결된다고 했다. 그 순간 느꼈다. 오, 해결됐다!!! 하지만 나의 반짝였던 기대감은 무너지고 해결되지 않았다. 각 페이지의 설정, 설정파일의 설정, 파일이름, 폴더이름을 늦은 밤까지 들여다봤지만 해결못한채 찜찜한 아침을 맞았다. 그리고 학원 가는 길, 새벽까지 블로그를 보다 잠들어서 피곤하여 힘이 쭉 빠져 있었다. 비몽사몽한 중에도 어제의 문제가 떠올랐다. 그리고 핸드폰을 들어 검색했다. jekyll pagination not working 많은 사람들이 너도나도 안된다고 글을 올렸고 많은 사람들이 도움을 주고자 답변을 달아놨다. 그러다 눈에 띈 글, index.html파일에서만 작동해요. 오, 파일명을 변경하고 경로에 폴더명을 추가해서 해결했어요! 아 그문제는 jekyll공식사이트에도 있어요. Jekyll-paginate-v2로 해결했습니다. 그리고 "Jekyll-paginate-v2 은 github.io에서는 작동하지 않아요." 나는 누구인가, 여기는 어디인가, 나는 어디로 가고 있는가, 삶이란 무엇인가. 안되는 이유가 다 있었다. 오전은 쉬고 오후에 다시 찬찬히 시도해보기로 했다. 사람들도 문제가 있고 물어보고 도와주면서 해결해가고 있었다. 나라고 못할 이유가 없다. Jekyll-paginate-v2를 지우고 다시 차근차근 폴더명과 파일명, 경로를 확인하고 Jekyll공식홈페이지에서 안내하는 설정문구를 작성했다. 어라? 되네?!

  수업시간에 선생님이 공식사이트를 계속 찾아주시면서 수업을 한 이유가 다 있었다. 내가 물어보는 즉시 바로바로 답을 내놓는 지피티가 편리해서 자꾸 묻다보니 돌고도는 답변속에서 (문제가 될만한 단서를 제시하지 않았기 때문에?) 밤을 지새웠지만, 안될 땐 얼른 다시 생각을 정리하고 마음을 가다듬고 다른 방법을 생각해야겠다. 개설한지 일주일만에 접을까 생각하게한 문제였지만, 가뿐하게 ㅋㅋ 잘 해결했고 할 수 있을 것 같다는 자신감이 불어와 나를 설레이게 하는 경험이었다.