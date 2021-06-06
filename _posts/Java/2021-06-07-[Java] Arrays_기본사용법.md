---
layout: post
title:  "Arrays 기본 사용법"
date:   2021-06-07
author: YoungHwan Kim
categories: Java
comment : true
tags:	Java
cover:  ""
---



## 1차원 배열의 비교 ##

```
package javacore;

import java.util.Arrays;

public class arraysTest01 {

    public static void main(String[] args) {

        int[] arr = {0,1,2,3,4};
        int[] arr2 = {0,1,2,3,4};

        System.out.println("배열비교 : " + Arrays.equals(arr,arr2)); // trueg
    }
}


```
