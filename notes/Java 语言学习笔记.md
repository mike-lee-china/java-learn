# Java 语言学习笔记

[TOC]

## 写在前面的话

一个计算机科班出身的人，一个在业内大厂工作多年的人，一个写C&C++/Bash但不精通的人，一个很多年不写代码的人。突然想起上学时候没有搞清楚 Java 语言，再重新开始学习，顺便做一下笔记，不知道能不能坚持到底，写到哪里算哪里。

因为有其他语言的基础，不会按照书本的顺序来学习，也不会按照书本的方式做笔记，按照遇到的问题展开来看，由问题引发。

## Hello World！

程序员和这个世界打招呼的方式，全球通用。先按照标准教程的方式和 Java 的世界打个招呼：Hello World。

```java
public class HelloWorld {
        public static void main(String[] args) {
                System.out.println("Hello Wrold");
        }
}
```

编译、运行：

```bash
$ javac HelloWorld.java
$ java HelloWorld
Hello Wrold
```

因为写 C/C++ 时候比较多，想是不是把 .java 文件和 .class 文件不放到一个目录中，这样可以把编译结果快速清理掉，git 提交的时候就不含 .class 文件，其实没必要，配置 .gitignore 就行了，[github](https://github.com/github/gitignore) 上直接就有各种语言模板可以使用，或者使用下面的这个：

```configure
# Compiled class file
*.class

# Log file
*.log

# BlueJ files
*.ctxt

# Mobile Tools for Java (J2ME)
.mtj.tmp/

# Package Files #
*.jar
*.war
*.nar
*.ear
*.zip
*.tar.gz
*.rar
```



作为一个了解 Android 构建工程的人，默认就是想把编译中间文件和编译结果放到 out 目录，so，就这么干了。那如何才能将编译结果放到 out 目录呢？javac 的各项参数出场了。

> [javac的使用](./javac的使用.md)

现在我们是想要将编译的 class 文件放到 out 目录中，不和源文件在一个目录。这个参数就是 *-d*

```bash
$ javac -d ../out/ HelloWorld.java
$ ls ../out/
HelloWorld.class
```

好了，我们成功的将 class 文件放到 out 目录了，现在我们要执行一下了，之前在源代码目录下直接执行的，现在还在源码目录下执行：

```bash
$ java ../out/HelloWorld
Error: Could not find or load main class ...out.HelloWorld
Caused by: java.lang.ClassNotFoundException: ///out/HelloWorld
```

咦，出现了什么？找不到！！！why？Linux 下程序不都是这么执行的吗？g++、clang 编译的 C/C++ 程序不都是可以吗？Python 也行，shell 脚本都没问题，javac 编译出来的为什么不行？凭什么！！！

