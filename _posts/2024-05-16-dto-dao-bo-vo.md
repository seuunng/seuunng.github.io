---
layout: post
title: DTO DAO VO BO
author: 개발자씅
categories: 
- 코딩
tags: 
keywords: 
date: 2024-05-16 10:00 +0800
lastmode: 2024-05-16 10:00 +0800
published: true
toc: true
excerpt: 
description: 
---
VO, BO, DAO, DTO는 소프트웨어 개발에서 객체지향 설계를 할 때 자주 사용되는 개념이다. 

## DAO (Data Access Object)
**: 데이터베이스 접근 담당, CRUD 작업 수행.**  
데이터베이스와의 상호작용을 담당하는 객체이다. CRUD(Create, Read, Update, Delete) 작업을 수행하며, 비지니스 로직으로 포함하지 않는다. DAO는 데이터베이스와의 상호작용을 추상화하여 데이터 접근 로직을 분리하고 재사용성을 높인다. DAO는 인터페이스를 통해 다양한 데이터 소스(DBMS)와 독립적으로 작동할 수 있다.  
예: UserDAO, ProductDAO는 사용자나 제품에 대한 데이터베이스 작업을 수행한다.

## DTO (Data Transfer Object)
**: 계층 간 데이터 전송 객체.**  
계층 간 데이터 전송을 위해 사용하는 객체이다. 보통 데이터베이스와의 상호작용이 없는 단순한 객체이다. DTO는 주로 네트워크를 통한 데이터 전송, 계층 간 데이터 이동 시에 사용된다. getter와 setter 메소드만을 가지고 있으며, 비즈니스 로직을 포함하지 않는다. 직렬화(Serialization)가 가능하며, 원격 호출 시 데이터 전송에 사용된다.  
예: UserDTO, OrderDTO는 사용자의 데이터나 주문 데이터를 네트워크를 통해 전송할 때 사용된다.

## VO (Value Object)
**: 불변 객체, 데이터 무결성 보장.**  
VO는 불변(immutable) 객체로서, 상태가 한 번 설정되면 변경되지 않는다. 주로 데이터 전달을 위해 사용된다. 데이터의 무결성을 보장하고, 데이터를 하나의 객체로 묶어 전달하기 위함위해 사용한다. 두 VO가 동일한지 비교할 때, 메모리 주소가 아닌 **상태(속성값)**를 비교하기 때문에 메모리 주소가 달라고 필드값이 같으면 같은 객체로 인식한다.

> **DTO VS VO와 비교**
DTO와 VO는 둘다 데이터를 **캡슐화**하고 복잡한 비즈니스 로직을 포함하지 않고 계층가 **데이터 전달**이 목적인 간단한 객체임이 비슷하지만, **VO**는 **불변 객체**인 반면, **DTO**는 보통 **가변 객체**이다.
**VO의 불변성은 다음 규칙을 따라야 함**  
    1. 모든 필드는 final이어야 한다.
    2. 객체 자체가 final이어야 한다.
    3. setter 메소드가 없어야 한다.(변경될수 없으니까!)
    4. 생성자에서 모든 필드를 초기화해야 한다.
    5. 필드가 참조하는 객체들도 불변 객체여야 한다.
이는 단순히 DTO(Data Transfer Object)를 final로 선언하는 것보다 더 깊은 의미를 가진다. DTO를 final로 선언하는 것은 그 클래스가 상속되지 않도록 하는 것일 뿐, 객체의 불변성을 보장하지 않는다. 
<br>
또한 VO는 주로 값의 동일성을 판단하기 위해 equals와 hashCode 메소드를 재정의하지만, DTO는 그렇지 않을 수 있다.


## BO (Business Object)
**: 비즈니스 로직 포함, 도메인 모델 표현.**  
비즈니스 로직을 포함한 객체로, 애플리케이션의 주요 비즈니스 로직을 담당한다.도메인 모델을 표현하고 비즈니스 로직을 캡슐화한다. 상태 유지하고 변경하는 역할한다. 데이터의 가공 및 변환을 책임진다.    
예: Order, Customer와 같은 객체는 주문 처리나 고객 관리와 같은 비즈니스 로직을 포함할 수 있다.

> **비즈니스로직**: 애플리케이션이 실질적으로 비즈니스 요구 사항을 충족시키기 위해 수행해야 하는 기능과 행동을 의미한다. 데이터를 생성, 읽기, 업데이트, 삭제(CRUD)하는 작업을 포함하여 **데이터를 처리하고 변환**한다. 혹은 비즈니스 규칙에 따라 수치 계산이나 데이터 집계 작업을 수행하거나 특정 작업이나 이벤트가 발생하는 순서와 조건을 관리한다.

> **도메인 모델**: 비즈니스 도메인을 이해하고 설명하기 위해 정의된 개념과 관계의 집합
**도메인**은 소프트웨어가 다루고자 하는 특정 비즈니스 영역이나 문제 공간을 의미
**모델**은 도메인을 이해하고 설명하기 위해 개념과 관계를 정의한 추상적 표현
BO가 도메인 모델을 표현한다는 개념은 BO가 특정 비즈니스 도메인(업무영역) 의 개념과 규칙을 객체로 나타낸다는 뜻이다.  
예) BO는 도메인 모델의 **비즈니스 개념을 캡슐화** 한다.(예: 주문, 고객, 제품의 개념을 객체로 나타냄), 
BO는 도메인 내의 **비즈니스 규칙을 구현**한다.(예: 주문이 생성될 때 규칙, 주문 상태의 변화 규칙 등),
BO는 도메인의 **상태와 행위를 표현**한다. 

>**상태를 가진다는 것**: Order 라는 BO를 가정할때 orderId, orderDate, status같은 속성으로 구성된다. 

여기서 **statu**s는 **처리중, 배송중, 완료** 등으로 상태를 나타낼 수 있다.

```
public class Order {
    private String orderId;
    private Date orderDate;
    private Customer customer;
    private List<Item> items;
    private String status;  // "Processing", "Shipped", "Delivered"

    // 생성자
    public Order(String orderId, Date orderDate, Customer customer) {
        this.orderId = orderId;
        this.orderDate = orderDate;
        this.customer = customer;
        this.items = new ArrayList<>();
        this.status = "Processing";
    }
```
주문 과정에 따라 status의 상태가 변화하고, 그에 따라 비즈니스 로직을 수행하도록 설계한다. 예를들어 status가 "Processing"인 경우에 shipOrder() 메소드를 호출할 수 있게 하고, 메서드가 시행되면  주문 상태를 "Shipped"로 변경할 수 있다.
```
public void shipOrder() {
        if ("Processing".equals(status)) {
            status = "Shipped";
        } else {
            throw new IllegalStateException("Order cannot be shipped in its current state");
        }
    }
```
이 과정에서 Order 객체의 status 속성 값이 "Processing" -> "Shipped" 변하게 하면서 비즈니스 로직에 실행되게 한다. 이런 과정에서 BO가 상태를 가진다고 한다. BO가 상태를 가진다는 것은 객체의 속성 값이 비즈니스 로직을 수행하면서 변할 수 있는 것을 의미하며, 이는 BO가 내부적으로 데이터를 유지하고 관리하는 것을 의미한다.

> DAO VS BO와 비교
BO: 비지니스 로직 포함. 상태유지, 비즈니스 로직에 따라 상태가 변할 수 있음
DAO: 비지니스 로직 포함하지 않음
<br>
DAO가 상태 변수를 가질 수 있지만, 이 상태는 데이터베이스와의 상호작용을 위한 것이다. 반면, BO는 비즈니스 로직을 수행하면서 도메인 데이터를 관리하고 변경하는 역할을 한다. 따라서 DAO의 상태 변수와 BO의 상태 변수는 목적과 사용 방식이 다르다.

## 마무리
DTO와 VO, DAO와 BO, 비슷한듯 다른 개념들에 대해서 살펴봤다. 비교해서 살펴보니 더 잘 이해가 된것 같다.