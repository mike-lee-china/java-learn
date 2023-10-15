## javac的使用

最准确的使用说明当然是官方文档了：https://docs.oracle.com/en/java/javase/11/tools/javac.html#GUID-AEEC9F07-CB49-4E96-8BC7-BCC2C7F725C9

官方文档向来是面面俱到，单看起来很累，我就用自己的理解，口语化简单讲讲，能简单解决遇到的问题就好，如果有更高的需要，那再去看官方文档吧。

### javac 的两种使用方式：

1. 直接使用命令 + 参数：我们先看这个。
2. 命令 + 参数文件（1 个或多个）：高级用法，有需要的时候再看。

``` bash
javac [options] [sourcefiles]
```

javac 不用讲了，这个就是工具在命令行中的工具命令，主要作用就是把 Java 的源文件（.java）编译成字节码(.class)，就是 Java 语言的编译器。

sourcefiles 就是需要编译的源文件列表，javac 一次可以编译多个，在上面看，这个参数也是可选的，那不输入是什么效果？试一下！

```bash
Usage: javac <options> <source files>
where possible options include:
  @<filename>                  Read options and filenames from file
  -Akey[=value]                Options to pass to annotation processors
  --add-modules <module>(,<module>)*
        Root modules to resolve in addition to the initial modules, or all modules
        on the module path if <module> is ALL-MODULE-PATH.
  --boot-class-path <path>, -bootclasspath <path>
        Override location of bootstrap class files
  --class-path <path>, -classpath <path>, -cp <path>
        Specify where to find user class files and annotation processors
 ……
```

现在我们知道了，官方文档中 [sourcefiles] 虽然是 **[]** 括起来了，但也并不是可选的，不输入的话，就直接提示使用方法了。

### javac options

javac 的编译选项（options) 分为三类：

1. Standard Options 标准选项
2. Cross-Compilation Options for javac 交叉编译 javac 选项
3. Extra Options 扩展选项

不打算翻译官方文档，在使用的时候，用到哪个，写哪个，后面遇到再回来补充。