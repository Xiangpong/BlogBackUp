---
title: 多线程与Java
date: 2019-06-06 16:55:21
tags: 笔记
categories: 笔记 
---

## 多线程

#### 进程与线程
* 进程：正在执行中的程序（应用程序在内存中运行的那片空间）

* 线程：进程中的一个执行单元，负责进程中程序的运行。一个进程中至少要有一个线程。

**一个进程中是可以有多个线程的，即多线程程序**

* 程序多线程的特点：可以实现多部分程序同时执行，即并发。

<!-- more -->

#### 多线程与CPU

我们都知道CPU是一个计算机运算的核心，这么说CPU很强咯，那是不是越高级的CPU，能同时执行线程越多？

其实不然。事实上，CPU在某一时刻只能执行一个线程。我们日常使用计算机时可以做到的这边听歌，那边打游戏，只是因为CPU太快了~ CPU在线程间进行快速切换快到你感觉不到。

例如我们要复制一个文件，在没有其他进程的干扰下可能只需要10分钟。当我们开着游戏听着歌的时候，复制这个文件的时间就会被延长15分钟甚至更长，这是因为CPU在多个线程间来回切换执行任务。

多线程可以合理使用CPU的资源，但如果线程过多，会导致CPU性能降低，即是“卡了”。

#### 创建线程

创建线程的两种方式：
* 继承Thread类
    1. 定义一个继承Teread的类
    2. 重写run()方法
    3. 创建线程对象
    4. 调用start方法

```java
class ThreadDemo extends Thread{
    private String name;
    ThreadDemo(String name){
        this.name = name;
    }
    public void run() {
        for (int i = 0; i <= 20; i++)
            System.out.println("name=" + name + "..." + i);
    }
}
 class ThreadTest{
    public static void main(String[]args){
        ThreadDemo d1 = new ThreadDemo("A");
        ThreadDemo d2 = new ThreadDemo("B");
       
        d2.start(); //d2线程开启，由子线程完成
        d1.run(); //d1仍由主线程完成
    }
}
```
线程对象调用run方法和调用start方法的区别：
* 调用run() 不开启线程，仅仅是对象调用方法
* 调用start() 开启线程，并让JVM调用run()在开启的线程中执行

q： 为什么不直接创建Tread类的对象呢？
```
    Thread t1 = new Thread();
    t1.start();
```
a： 创建Thread类的对象，并调用start方法时，调用的是Tread类中的run方法，而这个run方法我们并没有给定我们要执行的代码，所以是没有意义的。所以要继承Thead类来重写run方法。

---

* 实现Runnadle接口
    1. 定义类实现Runnable接口
    2. 覆盖run()方法
    3. 创建Thread类对象（只有创建Thread类对象才能实现线程）
    4. 将Runnable接口的之类对象作为参数传递给Thread类的构造函数
    5. 调用start方法开启线程

```java
class RunnableDemo implements Runnable {
    private String name;
    RunnableDemo(String name){
        this.name = name;
    }

    //覆盖了Runnable接口中的run（）方法
    public void run() {
        for (int i = 0; i <= 20; i++)
            //Thread.currentThread().getName() 获取当前线程名
            System.out.println("name=" + name + "..." +Thread.currentThread().getName()+"..."+ i);
    }
}

public class RunnableTest {
    public static void main(String[] args) {
        //创建Runnable之类的对象（它并不是线程对象）
        RunnableDemo rd = new RunnableDemo("rd");

        //创建Thread类的对象，将Runnable接口的之类对象作为参数传递给Thread类
        Thread t1 = new Thread(rd);
        Thread t2 = new Thread(rd);

        t1.start();
        t2.start();
    }
```

**实现Runnable接口和继承Thread类的区别：**

当需要多线程运行某类代码时，直接继承Thread类确实方便，但如果该类已经继承了其他类，我们就可以使用Runnable接口来实现多线程功能。避免了单继承的局限性。

使用Runnable接口实现多线程更加符合面向对象。线程分为两部分，一部分为线程对象，一部分为线程任务。
继承Thread类，线程对象和线程任务出现耦合，因为一旦创建Thread类的之类对象，就即是线程对象，又是线程任务。而Runnable接口，将线程任务单独分离封装成对象，类型就是Runable接口类型。
