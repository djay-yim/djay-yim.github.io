---
title: "Djay blog started"
last_modified_at: 2021-08-10
toc: true
toc_sticky: true
categories:
  - blog
tags:
  - jekyll
  - github
  - github pages
  - start
  - blog
  - djay
---

# #Blog #Github #Jekyll
## 2021.08.07
> 세월 참 빠르다.

### (내) Blog의 시작
> 개발자로 살다보면 검색을 참 많이하게 된다.  

#### 뫼비우스의 띠
1. 좋은 정보를 얻고, 좋은 글을 읽고 하다보면 자연스럽게 이런 생각이 든다.
2. 나도 **멋진 blog**를 갖고 싶다.
3. 어떤 플랫폼이 좋지? 네이버는 싫은데? 초대 받아야 된다구?
4. 어렵네.. 다시 1번으로 👆

#### His Story
- 내가 몇살이더라 서른마흔다섯살이였나..
- 서른마흔쉰살인가..
- 닭가슴살..
- 내일부터 다이어트 해야지..
- 아 공부해야되는데..
- 일에 치이고 삶에 치여 시간이 없다는 이유로 안하던 공부를 다시 시작했다.
- 기록하지 않으면, 했다는 기억조차 안 남을 것 같아 github에 push하기 시작했다.
- 오늘도 열심히 검색하고있다.
- 뭔가 눈에 밟힌다.
- github.io는 무슨 도메인이지? github에서 호스팅도 할수있나 ❓
- 응..❓ github계정만 있으면 무료로 ❓
- 응❓.. github로 블로그를 할수있네 ⁉️
- 어차피 github 에 push할거 블로그나 해볼까 ‼️

---

### ⭐️ Background to know
> Keywords

- Git : Git을 모를 경우 github + jekyll 구성이 크게 메리트가 없으므로 다른 플랫폼을 찾으시길 추천드립니다. 👋  
  ※ 물론 하고자 한다면 하시면 됩니다. 😀


- [Github](https://github.com/) : Git 저장소 호스팅을 제공
- [Github pages](https://pages.github.com/)
  - github 저장소 기반에 web 호스팅 제공
  - jekyll 과 결합해서 효율적인 blog site 작성 가능


- [Jekyll](https://jekyllrb-ko.github.io/)
  [(wiki)](https://en.wikipedia.org/wiki/Jekyll_(software)) :
  - Markdown언어로 Markup file 을 생성해주는 특징을 갖고있는 소프트웨어.
  - [[Markdown]](https://ko.wikipedia.org/wiki/%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4) file
    -> [[MarkUp]](https://ko.wikipedia.org/wiki/%EB%A7%88%ED%81%AC%EC%97%85_%EC%96%B8%EC%96%B4) file
  - 즉, jekyll을 이용해, 쉽게 html 작성가능.
    - e.g. index.md 작성 -> index.html 생성


- [Ruby](https://www.ruby-lang.org/ko/) : 프로그래밍 언어
- [Gem](https://www.ruby-lang.org/ko/libraries/) : library file of Ruby
- [Bundler](https://bundler.io/) : Ruby프로젝트의 library(gem) 의존성을 관리하는 Ruby gem
  - Gemfile 이라는 file로 관리
- [Rbenv](https://github.com/rbenv/rbenv) : Ruby 개발환경 소프트웨어 e.g. 버전관리 등

---

### ⭐ 끝..?  글을 마무리하며..🛬
> 👉 "github + jekyll" Blog 만들기 요약

1. [jekyll 테마를 고른다.](#-테마-선택하기)
2. [github repository 에 올린다.](#-github-repository-세팅)
3. github page로 세팅한다.
4. 참 쉽져?

> 👉 로컬세팅 - 개발자는 local세팅이 시작이라고 배웠습니다. 

1. [local 에 Ruby(Rbenv)를 설치한다.](#-local-server-세팅)
2. jekyll 테마를 넣어놓은 경로로 간다.
3. 번들러랑 지킬 gem을 설치한다.
  - gem install bundler jekyll
4. jekyll 서버 수행!!!!
  - bundle exec jekyll serve
5. 오류 메세지에 따라 설치하면서 계속 server를 띄우고자 한다.
6. 끝


> ⭐ Tips  

- Ruby 3.0 부터 webrick이 default gem에서 빠짐
  - 추가하려면 👇 
  - bundle add webrick 
- 👉 하단에 작업 log 날것 그대로 추가했습니다.

---

> 작성 환경  

- MacBook Air (M1, 2020) Apple M1
- OS : MacOS Big Sur 버전 11.3

---

### 🛫 **Take Off**

#### 👉 테마 선택하기
> 테마먼저 고르자, 보기좋은 블로그가 읽기도 좋다.

- jekyll 테마 관련 사이트👇가 많고, 테마는 훨씬 더 많다.
  - [http://jekyllthemes.org/](http://jekyllthemes.org/)


- TMI - 디자인 문외한인 나의 선택기준
  1. 내가 원하는 메뉴 구성인가? 커스텀이 용이한가? - 비슷해야 바꾸기 편하겠지?
  2. 검증된 테마인가? 많이쓰는 테마인가? - 나만 다른길을 걷고싶지않아.
  3. 최근에도 update가 되고있는 테마인가? - 우리들은 EOS를 싫어한다.
  4. 그래서 난 이거 ***https://github.com/mmistakes/minimal-mistakes***

---

#### 👉 Github repository 세팅
> fork or clone  

- 어느방법으로 해도 상관없음 본인 Github Repository에 copy!

---

> Github repository setting!  

- Settings
![img_11.png](/assets/images/20210807/20210807-img_11.png)
- Repository name 변경 (내계정명)
![img_12.png](/assets/images/20210807/20210807-img_12.png)
 
---

> clear files & set config  

- 샘플, 데모로 작성되어있는 파일들 삭제
- 사이트 이름도 내이름으로~
- [mmistakes 테마 가이드](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)

---
#### 👉 local server 세팅
> 설치지옥  

- Ruby Version Manager 설치
  - brew install rbenv
  - [ruby설치 잘 안되나여?](#---ruby-설치)


- bundler, jekyll 설치
  - gem install bundler jekyll
  - ![img.png](/assets/images/20210807/20210807-img.png)


- execute jekyll 서버!!!
  - bundle exec jekyll serve
  - ![img_1.png](/assets/images/20210807/20210807-img_1.png)


- 여기까지가 핵심.. 이 밑으로는 그냥 작업 log 


- bundle install
- ![img_2.png](/assets/images/20210807/20210807-img_2.png)
- bundle exec jekyll serve
- ![img_3.png](/assets/images/20210807/20210807-img_3.png)
- bundle exec jekyll serve --trace
- ![img_4.png](/assets/images/20210807/20210807-img_4.png)
- Gemfile <- docs/Gemfile 내용으로 교체
- bundle install
- ![img_5.png](/assets/images/20210807/20210807-img_5.png)
- ![img_6.png](/assets/images/20210807/20210807-img_6.png)
- bundle update
- ![img_7.png](/assets/images/20210807/20210807-img_7.png)
- bundle exec jekyll serve --trace
- ![img_8.png](/assets/images/20210807/20210807-img_8.png)
- bundle add webrick
- [reference](https://junho85.pe.kr/1850)
- ruby 3.0 부터 webrick 이 default gem에서 빠짐
- ![img_9.png](/assets/images/20210807/20210807-img_9.png)
- bundle exec jekyll serve --trace
- ![img_10.png](/assets/images/20210807/20210807-img_10.png)

#### 👉 custom
> 구조를 알아야 커스텀을 할텐데?
- [jekyll customizing 참고](https://www.jihyeleee.com/blog/third-designer-can-make-jekyll-blog/)

#### 👉 Ruby 설치
> 링크로 대체한다.
- [맥에서 루비하기 참고](https://dev-yakuza.posstree.com/ko/ruby-on-rails/rails-on-mac/)

#### 👉 뭐뭐 세팅해야되지?
> 귀찮다 일단 시작하자

## References
- [GitHub 블로그 시작하기](https://honbabzone.com/jekyll/start-gitHubBlog/)
- [mmistakes 테마 가이드](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)
- [Ruby설치부터 run 서버 까지](https://frhyme.github.io/blog/install_jekyll_again/)
- [맥에서 루비하기 참고](https://dev-yakuza.posstree.com/ko/ruby-on-rails/rails-on-mac/)
- [jekyll customizing 참고](https://www.jihyeleee.com/blog/third-designer-can-make-jekyll-blog/)

