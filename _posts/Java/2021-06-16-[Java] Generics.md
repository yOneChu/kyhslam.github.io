---
layout: post
title:  "[Java] 지네릭스(Generics)"
date:   2021-06-16
author: YoungHwan Kim
categories: Java
comment : true
tags:	Java,generics
cover:  "/assets/instacode.png"
---



# **지네릭스(Generics)** #
- 제네릭스는 다양한 타입의 객체들을 다루는 메서드나 컬렉션 클래스에 컴파일 시의  타입체크**(compile-time  type check)**를 해주는 기능이다.
- 객체의 타입을 컴파일 시에 체크하기 때문에 객체의 타입 안정성을 높이고 형변환의 번거로움이 줄어든다.

## 장점 ##
- 타입의 안정성을 높인다는 것은 의도하지 않은 타입의 객체가 저장되는 것을 막고, 저장된 객체를 꺼내올 때 원래의 타입과 다른 타입으로 잘못 형변환되어 발생할 수 있는 오류를 줄여준 다는 뜻이다.

- 즉, 다룰 객체의 타입을 미리 명시해줌으로써 번거로운 형변환을 줄여준다는 애기다.
