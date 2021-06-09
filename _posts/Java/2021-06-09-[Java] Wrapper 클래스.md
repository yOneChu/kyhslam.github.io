---
layout: post
title:  "[Java] Wrapper 클래스란?"
date:   2021-06-09
author: YoungHwan Kim
categories: Java
comment : true
tags:	Java,wrapper
cover: /assets/instacode.png
---



# **Wrapper 클래스** #

- 자바에서는 8개의 기본형은 객체로 다루지 않는다.
- 그러나 때로 기본형(primitive type) 변수도 어쩔 수 없이 객체로 다뤄야 하는 경우가 있다.
예를 들면, 기본형 값이 아닌 객체로 저장해야할 때, 객체간의 비교 시 등이 있다.
이때, 사용되는 것이 래퍼(wrapper) 클래스이다. 이 클래스들을 이용하면 기본형 값을 객체로 다룰 수 있다.

- 래퍼클래스들은 모두 equals()가 오버라이딩되어 있어서 주소값이 아닌 객체가 가지고 있는 값을 비교한다.

- 오토박싱이 된다고해도 Ingteger객체에 비교연산자를 사용할 수 없다. 대신 comparator()를 제공한다.


## **예제1** ## 
```
public class wrapper_test01 {

    public static void main(String[] args) {

        Integer i = new Integer(100);
        Integer i2 = new Integer(100);

        System.out.println("i==i2 " + (i==i2));
        System.out.println(i.equals(i2)); // true
        System.out.println(i.compareTo(i2)); // 0
        System.out.println(i.toString()); // 100

        System.out.println(Integer.MAX_VALUE); // 2147483647
        System.out.println(Integer.MIN_VALUE); // -2147483648
        System.out.println(Integer.SIZE); // 32
        System.out.println(Integer.BYTES); // 4
    }
}

```


