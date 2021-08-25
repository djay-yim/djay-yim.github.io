---
title: "Performance? Testing?"
last_modified_at: 2021-08-24
toc: true
toc_sticky: true
categories:
  - testing
tags:
  - performance
  - testing
---

# #Performance
## 2021.08.24
> 성능 테스트

개발을 하다보면 필연적으로 성능에 포커싱 되는 케이스들을 만나게된다.  
그런 케이스들은.. 내 경험에 비추어 봤을때 보통 이런 단어들이 뒤따라 온다.  

👉 TPS, 동시사용자수, 접속자수, 초당요청건수, 분당주문건수,,,  

대충 나열한 단어들만 봐도 알 수 있다. 우리는 숫자가 필요하다.  

사용중인 모니터링 툴이나 분석툴 을 통해 원하는 수치를 확인할 수 있고,  
축적된 대조 가능한 데이터까지 있다면 금상첨화다.  
숫자를 확인하고 전략을 세우고 적용하고 확인하면 된다.  

**끝.**  

> 그러나 ?  

그렇지 않다면 ?

우리는 숫자를 만들어야 한다.
되도록이면 나에게 유의미한 숫자를..😈  
근데 어떻게 만들지?

---


## 👇 Show me the numbers 

### ⭐️ [AB - Apache HTTP server benchmarking tool](https://httpd.apache.org/docs/2.4/ko/programs/ab.html){:target="_blank"}

> 아파치 웹서버 성능검사 도구

#### Features
- CLI에서 명령어 한번 날려주면 http요청에 대해 숫자를 볼 수 있다.
- [docs]((https://httpd.apache.org/docs/2.4/ko/programs/ab.html))에 보면 옵션이 굉장히 많다. 대충 필요한거 2개만 봐보자.
  - n : requests, 요청수. default=1
  - c : concurrency, 동시에 요청하는 요청수. default=1
- 일단 이거 2개만 알고 밑에 예제를 봐보자. 

⭐️ **Please Note!**   
👉 MAC 이나 Linux OS엔 대부분 설치 되어있다. Windows라면 설치해야 사용가능..
{: .notice--danger}

#### Using 👇
```shell
ab -n 100 -c 10 https://www.naver.com/include/themecast/targetAndPanels.json
```
👇 Result 
![ab-result.png](/assets/images/20210824/ab-result.png)


---

### ⭐️ [Jmeter](https://jmeter.apache.org/){:target="_blank"}

> 아파치 재단의 어플리케이션으로..

The Apache JMeter™ application is open source software, a 100% pure Java application designed to load test functional behavior and measure performance.
It was originally designed for testing Web Applications but has since expanded to other test functions. 

#### Features
- bin/jmeter 로 실행
  - options 
    - n : CLI로 실행하겠다. 👉 안넣으면 GUI로 실행
    - t : 뒤에 XML로 저장된 테스트파일 경로를 넣는다.
- GUI 에서 테스트를 작성하고, CLI에서 수행 하는게 권장된다.
- 테스트 설정은 .jmx 확장자로 저장되고, 내용을 보면 XML 형태다.
- 테스트 설정은 필요에 따라 학습하면서 쓰기 어렵지 않다.
  - 나는 인증을위해 get method에 http header추가 정도만 해봤다.
  - 어렵지 않고 중요한 것도 아니여서 자세한 내용은 안남긴다. 

#### Using 👇
👇 GUI 수행
```shell
bin/jmeter
```

👇 CLI 수행
```shell
bin/jmeter -n -t ../tests/TestHello.jmx
```

⭐️ **Please Note!**   
👉 [download link](https://jmeter.apache.org/download_jmeter.cgi){:target="_blank"}
{: .notice--danger}

---

### 🛬 마무리
> 새삼스럽게 갑자기 마무리한다. 항상 그래왔듯이.. 너무 졸리다.

#### Insight 👀
- 내 경험에 비추어 봤을때 대부분의 경우 성능테스트로 명확한 답을 찾기는 어려웠다.
- 결국 테스트란 about 이고, 고객 혹은 상사들을 위한 보고용 숫자 메이킹에 불과한 경우가 많았다.
- 하지만 그안에서 유의미한 숫자를 선별하고 개선 전략을 찾아가는 과정은 분명히 필요하다고 생각한다.
- 결국 좋은결과를 얻으려면 데이터를 얼마나 "잘" 선별하고, 전략을 "잘" 세우고, "잘" 수행하는 "잘" 의 영역 이지만
- 성능은 숫자없이는 논할 수 없는 영역이기에, 내 서비스에 대한 최소한의 숫자는 갖고다니자 🤟
- 이런건 믿음으로 가는거지.. 응..?

## References
- [https://httpd.apache.org/docs/2.4/ko/programs/ab.html](https://httpd.apache.org/docs/2.4/ko/programs/ab.html){:target="_blank"}
- [https://jmeter.apache.org/](https://jmeter.apache.org/){:target="_blank"}