---
layout: post
title: If else和switch case的区别和原理
comments: true
author: "Yin Haomin"
tags:
    - if else
    - switch case
---

谈谈对if else和switch case的区别。if，else支持任意的变量的比较。而Java目前支持了switch，case对于基础变量和String的支持。构造的对象的比较则不能够支持。<br>
那么，switch case是怎么做的支持呢？我们可以直接看下相关的代码的反编译的代码<br>
对于基础变量的支持
```
    public static void main(String[] args) {
        int i = 0;
        int n = 0;
        switch (i) {
            case 101:
                n = 1;
                break;
            case 102:
                n = 2;
                break;
            case 103:
                n = 3;
                break;
            default:
                n = 0;
                break;
        }
    }
```
反编译以后
```
    public static void main(String args[])
    {
        int i = 0;
        int n = 0;
        switch(i)
        {
        case 101: // 'e'
            n = 1;
            break;

        case 102: // 'f'
            n = 2;
            break;

        case 103: // 'g'
            n = 3;
            break;

        default:
            n = 0;
            break;
        }
    }
```

对于String的支持
```
    public static void main(String[] args) {
        String mode = "333";
        switch (mode) {
            case "ACTIVE":
                System.out.println("Application is running on Active mode");
                break;
            case "PASSIVE":
                System.out.println("Application is running on Passive mode");
                break;
            case "SAFE":
                System.out.println("Application is running on Safe mode");
                break;
            default:
                break;
        }
    }
```
反编译以后
```
    public static void main(String args[])
    {
        String mode = "333";
        String s;
        switch((s = mode).hashCode())
        {
        default:
            break;

        case -74056953: 
            if(s.equals("PASSIVE"))
                System.out.println("Application is running on Passive mode");
            break;

        case 2537357: 
            if(s.equals("SAFE"))
                System.out.println("Application is running on Safe mode");
            break;

        case 1925346054: 
            if(s.equals("ACTIVE"))
                System.out.println("Application is running on Active mode");
            break;
        }
    }
```
这个相关联的，就是在Object中，怎么对象进行比较。<br>

