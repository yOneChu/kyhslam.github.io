---
layout: post
title:  "[Java] Arrays_기본 사용법"
date:   2021-06-08
author: YoungHwan Kim
categories: Java
comment : true
tags:	Java
cover:  ""
---



- Arryas클래스는 배열을 다루는데 유용하다.


## binarySearch ##
- **binarySearch()** 는 반드시 배열이 정렬된 상태에서만 올바르게 작동한다.
- 그리고 주의할 점은 배열에 검색한 값과 일치하는 요소들이 중복으로 있으면 어떤 것의 위치가 반환될지 알 수 없다.
```
package org.kyhslam.collectEx;

import java.util.Arrays;
import java.util.List;

public class arraysTest01 {

    public static void main(String[] args) {
        int[] arr = {3,2,0,1,4};
        int[] arr2 = {3,2,9,10,43};
        int[][] arr2D = {{11,12},{21,22}};
        int[][] arr2D2 = {{11,72}, {21,82}};
        String[] str = {"11", "22", "33"};

        Arrays.sort(arr);
        System.out.println(Arrays.toString(arr));
        int idx = Arrays.binarySearch(arr, 2);  // idx = 2
        // binarySearch는 반드시 배열이 정렬된 상태에서만 올바른 결과를 얻는다.
        // 그리고 검색한 값과 일치하는 요소들이 있으면 어떤 것의 위치가 반환될지 알수없다.
    }

}
```



## 배열의 출력 방법 ##
```
System.out.println(Arrays.toString(arr)); // 1차원
System.out.println(Arrays.deepToString(arr2D)); // 2차원 이상
System.out.println(Arrays.toString(str)); // 문자열도 출력 가능
```


## 배열 비교 방법 ##
- Arrays.equals(a,b)
- Arrays.deepEquals(a,b)
```
System.out.println(Arrays.equals(arr, arr2)); // 1차원 배열 비교  false
System.out.println(Arrays.deepEquals(arr2D, arr2D2)); // 2차원 배열 이상의 비교 false
```

## asList 사용법 ##
- **Arrays.asList()** 는 배열을 List에 담아서 반환한다.
- 주의할 점은 asList()가 **반환한 List의 크기는 변경할 수 없다.**
```
// 방법1 
List list = Arrays.asList(new Integer[] {1,2,3,4,5});   // [1, 2, 3, 4, 5]

// 방법2
List list2 = Arrays.asList(1,2,3,4,5); // [1, 2, 3, 4, 5]
```



