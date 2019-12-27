# V8 run script

> 既有解释器 Ignition，又有编译器 TurboFan

## 编译器（Compiler）

> 编译型语言在程序执行之前，需要经过编译器的编译过程，并且编译之后会直接保留机器能读懂的二进制文件，这样每次运行程序时，都可以直接运行该二进制文件，而不需要再次重新编译了

在编译型语言的编译过程中，编译器首先会依次对源代码进行

1. 词法分析
2. 语法分析，
3. 生成抽象语法树（AST），
4. 优化代码，
5. 生成处理器能够理解的机器码。
 True  可执行的文件
 False 编译器就会抛出异常


## 解释器（Interpreter）

>解释型语言编写的程序，在每次运行时都需要通过解释器对程序进行动态解释和执行 

1. 词法分析、
2. 语法分析，
3. 生成抽象语法树（AST），
4. 基于抽象语法树生成字节码，
5. 根据字节码来执行程序、输出结果。

## 抽象语法树（AST）

## 字节码（ByteCode）

> 字节码就是介于 AST 和机器码之间的一种代码。但是与特定类型的机器码无关，字节码需要通过解释器将其转换为机器码后才能执行。

## 即时编译器（JIT）

### 执行一段 JavaScript 代码

1. 将源代码转换为抽象语法树，并生成执行上下文
   1. 分词（tokenize），又称为词法分析
   2. 解析（parse），又称为语法分析
2. 生成字节码
3. 执行代码

### 性能优化

1. 提升单次脚本的执行速度，避免 JavaScript 的长任务霸占主线程，这样可以使得页面快速响应交互；
2. 避免大的内联脚本，因为在解析 HTML 的过程中，解析和编译也会占用主线程；
3. 减少 JavaScript 文件的容量，因为更小的文件会提升下载速度，并且占用更低的内存。