---
layout: post
title: 익숙하지만 낯선 코드, 접근제한자와 Java키워드
author: 개발자씅
categories: 
- 코딩
tags: accessModifier, JavaKeyword
date: 2024-05-01 20:00 +0800
lastmode: 2024-05-01 20:00 +0800
sitemap:
  changefreq: daily
  priority : 1.0
published: true
toc: true
excerpt: 근로자의 날을 맞이하여 수업시간에 본 모르는 코드 공부하기
---

근로자의 날인데도 수업을 들으러 간다. 익숙한 등원 길에 마주치던 귀여운 잼민이도 엘레베이터 앞에 줄 서있는 직장인들도 없는 낯선 아침이었다. 근로자의 날인데 초등학생은 왜 쉬는걸까하는 궁금증을 뒤로 한채 공부할 기분이 안나는 무겁고 늘어지는 적막한 아침 공기를 뚫고 교실에 들어선다. 수업을 듣다보면 강사님의 코드를 따라쓰고 오타 확인하기 바빠 내가 무슨 코드를 쓰고 있는 건지 미처 생각하지 못할 때가 있다. 또 다르게는 자주봐서 매우 익숙하나 무슨 뜻인지 모르는 코드들도 있다. 오늘은 무슨 뜻 인지도 정확히 모르고 강사님이 쓰는대로 따라 썼던 **익숙하지만 낯선 코드**에 대해서 공부해보고자 한다.

## 접근제한자
클래스, 메서드, 필드와 같은 자바 언어 요소에 대한 **접근 수준을 정의**하는 데 사용되는 키워드로 이를 통해 특정 코드의 접근 가능 정도를 제어하고, 외부에서 사용 허용할 지 여부를 결정한다. 어떤 접근제한자를 붙여서 만드느냐에 따라서 접근할 수 있는 범위가 달라진다는 얘기다. 으, 접근제한자에 대해서 잘 파악하지 못하고 아무거나 따라 썼다가는 도대체 왜 안되는거야!!를 백만번 외쳐도 왜인지 못 찾는 불상사가 생기기 십상이겠다. 그러니 오늘 아주 확실히 파악해 두자.


### public
모든 클래스에서 접근할 수 있는 **가장 제한이 없는** 접근제한자로 클래스, 메서드, 필드에 사용 가능하다. 가장 자주 보인것 같다. 공공의 이런 뜻일까? 다행히 별 제한 없이 다 사용할 수 있게 허용한다. 같은 패키지가 아니라도, 상속관계가 아니라도 접근을 허용하는 시골집 마당에서 키우는 귀여운 발바리 강아지 같은 접근제한자였다. 보안이 필요한 경우에는 주의할 필요가 있겠다. 기억하자.

```bash
// Public 클래스
**public** class PublicClass {
    // Public 생성자
    **public** PublicClass() {}
}
```
 
### protected
상속받은 **하위 클래스** 혹은 **동일한 패키지의 클래스**에서만 접근할 수 있다. 외부 패키지에서는 접근할 수 없지만 **상속 관계**에 있는 경우에는 접근할 수 있다. 보호하는 이라는 뜻일까? 외부의 접근은 차단하여 보호한다. 그래도 상속받은 클래스에게는 접근을 허용한다는 여지를 남긴다.

```bash
// Protected 클래스
class ProtectedClass {
    // **Protected** 생성자
    protected ProtectedClass() {}
}
```

### default: 패키지 프라이빗
접근 제한자를 명시하지 않을 때 **기본값**으로 적용되는 접근제한자로 **같은 패키지 내의 클래스**에서만 접근할 수 있다. 접근 수준은 protected보다 더 제한적이라고 볼 수 있다. protected는 외부라도 상속관계인 경우에는 접근을 허용하는 조건이 있지만 이 경우에는 어떠한 조건따위 없이 무조건 다른 패키지에서의 접촉은 차단하는 접근제한자다.

```bash
// Package-private 클래스
class PackagePrivateClass {
    // Package-private 생성자
    PackagePrivateClass() {}
}
```

### private
**해당 클래스 내부**에서만 접근할 수 있다. 이것도 많이 봤는데 이렇게 도도한 접근제한자 였다니 다시 보인다. 가장 접근 제한이 강력한 수준으로 다른 클래스나 하위 클래스(자식클래스나 파생클래스)에서도 접근할 수 없다.

```bash
// Private 클래스
class PrivateClass {
    // Private 생성자
    **private** PrivateClass() {}

    // 내부에서만 접근 가능한 메서드
    public static PrivateClass getInstance() {
        return new PrivateClass();
    }
}
```
> *비교 **로컬클래스**: private 클래스는 외부에서 클래스에 접근하는 것을 막는 것이고, 로컬클래스는 클래스 안에 생성된 클래스를 정의하는 것으로 해당 속한 클래스나 메서드, 블록 내부에서만 사용되는 클래스를 말한다. 제한적이라는 것은 비슷하지만, 개념 자체가 달라서 비교를 할 수 가 없다.. 

## Java 키워드

### static 
static은 **정적** 키워드로, 해당 메서드 또는 변수가 **클래스 수준**에 속함을 나타낸다. 즉, 클래스의 인스턴스화 없이도 메서드를 호출 할 수 있다. 클래스 로딩 시 메모리에 할당된다. 일반적으로 클래스 수준의 유틸리티 메서드 또는 상수를 정의할 때 사용된다.

```bash
public class Example {
    public **static** int counter = 0; // static 필드

    public **static** void increment() { // static 메서드
        counter++;
    }
}
```

### final 
final 키워드는 변수, 메서드, 또는 클래스를 **수정하지 못하도록** 제한할 때 사용된다. 변수에서 final이 사용되면 값이 변할 수 없고, 재할당할 수 없음을 의미한다. 이는 상수와 비슷하지만 상수는 컴파일 시부터 정해져 있는 값을 의미하고 변수를 final로 정의한다는 것은 초기화한 후에 변경할 수 없다는 것을 의미한다. 클래스 변수에 final과 static을 동시에 사용하면 컴파일 시점에 상수로 동작하게 되어, 프로그램이 실행하는 동안 변경할 수 없다. final이 메서드에서 사용되면 서브클래스에서 오버라이딩할 수 없음을 의미한다. 클래스에서 사용되면 서브클래스를 만들 수 없음을 의미한다.

```bash
public **final** class FinalClass { // 상속 불가능한 클래스
    public final void display() { // 오버라이딩 불가능한 메서드
        System.out.println("Final Method");
    }
}
public class Example {
    public **final** int CONSTANT_VALUE = 42; // 상수
}
```
> * **상수**란? 상수는 프로그램에서 변경할 수 없는 값이다. 한 번 정의되면 재할당 할 수 없으며, 프로그램의 나머지 부분에서 계속해서 사용합니다. 상수는 보통 프로그램에서 의미가 명확하고 변하지 않는 값을 표현하기 위해 사용된다.

### main
main 메서드는 Java **애플리케이션의 진입점**으로, 프로그램 시작 시 호출되는 메서드다.JVM(Java Virtual Machine)이 프로그램을 실행할 때 main 메서드를 찾아 실행한다. 일반적으로 public static void main(String[] args)의 형태를 취한다. String[] 타입의 매개변수를 받아서 프로그램에 전달된 명령줄 인자를 처리할 수 있다.

```bash
public class MainClass {
    public static void **main**(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### void
void 키워드는 메서드가 **반환값을 갖지 않음**을 나타낸다. 

```bash
public **void** printMessage(String message) {
    System.out.println(message);
}
```