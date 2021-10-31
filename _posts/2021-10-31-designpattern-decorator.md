---
title: "Designpattern - Decorator"
last_modified_at: 2021-10-31
toc: true
toc_sticky: true
categories:
  - java
tags:
  - java
  - designpattern
  - design
  - pattern
  - decorator
---

# #DesignPattern #Decorator
## 2021.10.31
> Runtime에 확장 기능을 조합(추가, 변경, 제거) 할 수 있도록 해 주는 패턴

## ⭐️ CookBook
1. Service Interface 생성
2. Service 구현 class 생성
3. Decorator class 생성
    - Service Interface(1번)을 내부 필드로 갖고 생성자로 주입받도록 작성
    - override methods는 내부필드에 위임(delegation) 처리

    ```java
    public class PrintDecorator implements PrintService {
    
      private PrintService printService;
    
      public PrintDecorator(PrintService printService) {
        this.printService = printService;
      }
    
      @Override
      public void print(String message) {
        printService.print(message);
      }
    }
    ```
4. 3번을 상속하는 Decorator class 구현
    ```java
    public class SmilingPrintDecorator extends PrintDecorator {
    
    	public SmilingPrintDecorator(PrintService printService) {
    		super(printService);
    	}
    
    	@Override
    	public void print(String message) {
    		super.print(addSmile(message));
    	}
    
    	private String addSmile(String message) {
    		return message + " :-)";
    	}
    }
    ```

## 마무리 🛬
### 고려할점 👇
- 💢 예외처리
  - 확장기능에서 예외 발생시 어떻게 처리할것인지?
    - e.g. 확장기능에서 예외발생해도 본기능은 동작하도록 처리


### 장점 👇
- Runtime에 확장 기능을 조합(추가, 변경, 제거) 가능
- 확장기능이 기존기능에 영향을 주지 않음
- 확장기능 클래스가 분리되므로 단일책임원칙 설계 용이

### 단점 👇
- 정의된 기능(method)이 많을 경우 복잡도 증가
  - method의 수가 많다면, decorator 구현 복잡도 증가
- 데코레이터와, 구현 객체의 구분이 되지않아 코드만으로 분석이 쉽지 않다.

## References
- 개발자가 반드시 정복해야할 객체 지향과 디자인 패턴 / 인투북스 / 최범균 지음