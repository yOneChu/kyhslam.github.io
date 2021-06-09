---
layout: post
title:  "[Java] Comparable_Comparator.md"
date:   2021-06-09
author: YoungHwan Kim
categories: Java
comment : true
tags:	Java,Comparable,Comparator
cover:  ""
---


# Compare()와 CompareTo() #

- compare()와 compareTo()은 선언형태와 이름이 약간 다를뿐 두 객체를 비교한다는 같은 기능을 목적으로 고안된 것이다.
- compareTo()의 반환값은 int이지만 실제로는 비교하는 두 객체가 같으면 0, 비교하는 값보다 작은면 음수, 크면 양 수를 반환한다.

- **Comparable** : 기본 정렬기준을 구현하는데 사용
- **Comparator** : 기본 정렬기준 외에 다른 기준으로 정렬하고자할 때 사용



## **예제1** ##

- 참고로 알파벳 문자열은 기본 정렬 시 대문자 먼저정렬하고 소문자가 정렬된다.


```
import java.util.Arrays;
import java.util.Comparator;

public class compareTest02 {

    public static void main(String[] args) {

        String[] strArr = {"cat", "Dog", "lion", "tiger"};
        System.out.println("11 :: " + Arrays.toString(strArr));

        Arrays.sort(strArr);
        System.out.println("22 :: " + Arrays.toString(strArr));  // 22 :: [Dog, cat, lion, tiger]

        Arrays.sort(strArr, String.CASE_INSENSITIVE_ORDER); // 대소문자 구분안함
        System.out.println("33 :: " + Arrays.toString(strArr)); // 33 :: [cat, Dog, lion, tiger]

        Arrays.sort(strArr, new Decending()); // 역순정렬
        System.out.println("44 :: " + Arrays.toString(strArr)); // 44 :: [tiger, lion, cat, Dog]
    }
}

class Decending implements Comparator {
    @Override
    public int compare(Object o1, Object o2) {
        if(o1 instanceof Comparable && o2 instanceof Comparable) {
            Comparable c1 = (Comparable)o1;
            Comparable c2 = (Comparable)o2;

            return c1.compareTo(c2) * -1;
        }
        return -1;
    }
}

```


## **예제2** ##

```
import java.util.Arrays;
import java.util.Comparator;

public class compareTest01 {

    public static void main(String[] args) {

        /**
         *
         * compare()와 compareTo()은 선언형태와 이름이 약간 다를뿐 두 객체를 비교한다는 같은 기능을 목적으로
         * 고안된 것이다.
         *
         * compareTo()의 반환값은 int이지만 실제로는 비교하는 두 객체가 같으면 0, 비교하는 값보다 작은면 음수
         * 크면 양 수를 반환한다.
         *
         * Comparable - 기본 정렬기준을 구현하는데 사용
         * Comparator - 기본 정렬기준 외에 다른 기준으로 정렬하고자할 때 사용
         *
         *
         */

        String[] str = {"3", "30", "34", "5", "9"};

        Arrays.sort(str);
        System.out.println(Arrays.toString(str)); // 문자 앞자리로 오름차순 정렬

        System.out.println();
        System.out.println();

        Arrays.sort(str, new Comparator<String>() {
            @Override
            public int compare(String o1, String o2) {

                //System.out.println(Arrays.toString(str));
                //System.out.println(o1 + " + " + o2 + " ==> " + o1+o2 + " :: " + o2+o1);
                return o2.compareTo(o1);
            }
        });

        System.out.println("result ::: " + Arrays.toString(str));  // result ::: [9, 5, 34, 30, 3]
    }
}



```
