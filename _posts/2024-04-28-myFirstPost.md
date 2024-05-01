---
layout: post                      # 사용할 레이아웃 파일 지정
title: 대망의 깃허브 블로그 첫 포스트!    # 포스트 제목
date: 2024-04-28 13:27 +0800      # 포스트 날짜 및 시간 (타임존 포함)
#last_modified_at:                 # 최근 수정 날짜
pagination:
  enabled: true
toc:  true        # 목차(Table of Contents) 활성화 여부
#tags:             # 이 포스트와 관련된 태그 목록
author: seuunng       # 글쓴이
#excerpt:          # 목차에 보여줄 요약, 한쓰면 본문 첫줄들어감
#published:        # false 로 처리하면 블로그에서 안보임
---
일단은 **한글**이 잘 써지는 테스트를 할 필요가 있다.


사이드바에 사진을 변경하는데도 얼마나 오래걸렸는지
커스텀을 다양하게 할 수 있는데 깃허브블로그의 장점이라는데
내가 잘 해낼수 있을지 아직 모르겠다. 
이렇게 쓰면 노란색 박스안에 들어간다.
{: .message } 

그래도 이 검은 화면에 무언가 이렇게 쓰고 있는걸
누군가 본다면 내가 엄청난 개발자라고 생각할지도..

나는 [깃허브](https://github.com/seuunng)와  유튜브, 네이브블로그를 운영하고 있어서
사이드바에 각 아이콘과 링크를 넣어 두었다. 
이것도 상당히 오려걸렸지만 해내고 나니 뿌듯하다.
사실 네이블 블로그 아이콘을 넣고 싶었는데,
실패하고 블로그 아이콘으로 대체했다. 
네이버 주주로서 네이버가 흥해서 <a href="https://fontawesome.com/">폰트어썸</a> 같은 글로벌 아이콘 사이트에 아이 
네이버 아이콘도 나와서 한국사람들이 편하게 코딩할 수 있는 날이 오기를 기대해 본다. 

지금은 연습중이니 포스트에 엉뚱한 소리가 있어도 이해해 주세요

> 이렇게 쓰면 옅은 회식으로 써지고 앞에 막대기가 생긴다. 인용구로 사용할 수 있을 것 같다.

## 소제목으로 사용할 수 있다. 

1. **To bold text**, use `<굵은글씨>`.
2. *To italicize text*, use `<기울임>`.
3.  <mark>To highlight</mark>, use `<강조, 형광펜>`.
- Abbreviations, like <abbr title="HyperText Markup Langage">HTML</abbr> should use `<마우스 올리면 줄임말표시 혹은 부제목 있을때 활용가능>`, 점선 밑줄 추가 회색글씨
- Citations, like <cite>&mdash; Mark Otto</cite>, should use `<책제목>`.
- <del>Deleted</del> text should use `<글자 가운데 줄>` and <ins>inserted</ins> text should use `<글자 밑줄>`.

<줄바꿈 안하면 위에랑 연결됨 더 들여쓰기가 된다던가
4번으로 표시된다던가 >
- 은 점으로 보여짐 ㅋㅋ 들여쓰기
1. 들여쓰기 연번


### 코드입력시

{% highlight js %}
// Example can be run directly in your JavaScript console

// Create a function that takes two arguments and returns the sum of those arguments
var adder = new Function("a", "b", "return a + b");


{% endhighlight %}

{% highlight js linenos %}
// 코드입력 줄넘버와 함께

// Create a function that takes two arguments and returns the sum of those arguments
var adder = new Function("a", "b", "return a + b");

{% endhighlight %}

### Lists
<dl>
  <dt>소제목HyperText Markup Language (HTML)</dt>
  <dd>들여쓰기 내용The language used to describe and define the content of </dd>

  <dt>소제목 Cascading Style Sheets (CSS)</dt>
  <dd>들여쓰기 내용 Used to describe the appearance of Web content</dd>

</dl>

### 크기별로 사진 넣기

![placeholder](http://placehold.it/800x400 "Large example image")
![placeholder](http://placehold.it/400x200 "Medium example image")
![placeholder](http://placehold.it/200x200 "Small example image")

Align to the center by adding `class="align-center"`:

![placeholder](http://placehold.it/400x200 "Medium example image"){: .align-center}

### Tables

Aenean lacinia bibendum nulla sed consectetur. Lorem ipsum dolor sit amet, consectetur adipiscing elit.

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Upvotes</th>
      <th>Downvotes</th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <td>Totals</td>
      <td>21</td>
      <td>23</td>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <td>Alice</td>
      <td>10</td>
      <td>11</td>
    </tr>
  </tbody>
</table>

Nullam id dolor id nibh ultricies vehicula ut id elit. Sed posuere consectetur est at lobortis. Nullam quis risus eget urna mollis ornare vel eu leo.

-----
<hr/> 위에꺼도 수평선이네 신기

Want to see something else added? <a href="https://github.com/vszhub/not-pure-poole/issues/new">Open an issue.</a>

