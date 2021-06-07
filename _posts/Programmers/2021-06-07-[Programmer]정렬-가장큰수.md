---
layout: post
title:  "[정렬] 가장큰수"
date:   2021-06-07
author: YoungHwan Kim
categories: 프로그래머스
comment : true
tags:	알고리즘
cover:  ""
---




```
package com.hyosung.algo;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.Comparator;


// 정렬 - 가장큰수 level.2
public class pro_sort_p02 {

    static int[] buff;
    static boolean[] visited;



    public static void main(String[] args) {

        //int[] numbers = {6,10,2};

        int[] numbers = {3,30,34,5,9};
        //int[] numbers = {0,4,1};


        String result = solution(numbers);
        System.out.println("result: " + result);
    }


    static void viewArray(int[] a) {
        for(int i=0; i < a.length; i++) {
            System.out.print(a[i] + " ");
        }
    }

    static void viewStrArray(String[] a) {

        for(int i=0; i < a.length; i++) {
            System.out.print(a[i] + " ");
        }

    }


    public static String solution(int[] numbers) {
        String answer = "";

        String[] str = new String[numbers.length];

        //int배열 String 배열로 변환
        for(int i=0; i < numbers.length; i++) {
            str[i] = String.valueOf(numbers[i]);
        }

        viewStrArray(str);
        System.out.println();

        //내림차순 정렬
        Arrays.sort(str, new Comparator<String>() {
            @Override
            public int compare(String a, String b) {
                System.out.println();
                viewStrArray(str);
                System.out.println();
                System.out.println(a + " :: " + b);
                System.out.println();

                return (b+a).compareTo(a+b);
            }
        });

        System.out.println();
        viewStrArray(str);
        
        //0값이 중복일경우 ex){0,0,0}
        //답이 000이 나오면 안되므로 첫번째값이 0이면 0을 리턴
        if(str[0].equals("0")){
            return "0";
        }

        for(String s : str) answer += s;
        
        return answer;
    }
}

```
