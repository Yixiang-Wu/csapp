1. 信息就是bit+context
    - ASCII码8位(bit)，1个字节(byte)，其中最高位不表示信息，0~127
    - 只由ASCII码字符构成的文件称为文本文件（text），其他的文件称为二进制文件
    - 对于一串同样的bit流，区分他们的方式是（context），也就是用什么样的规则去解释(interpretation)
2. 翻译过程
    1. pre-process(cpp)将include的内容插入到hello.c，处理宏，得到hello.i
    2. compiler(cc1)将hello.i变成汇编文件hello.s，注意这里每一条汇编语句都对应着一条低级的机器语言指令
    3. assembler(as)将hello.s翻译成机器语言指令，并打包成可重定位目标程序（relocatable object program）的格式，得到hello.o（binary file).
    4. linker(ld)。比如hello.c使用了printf函数，那么就要合并printf.o和hello.o，得到hello(binary file)。
3. 计算机结构
    1. 总线(buses)。用来传递信息，通常设计是传送字(word)。大多数机器字长要么是4个字节，要么是8个字节。
    2. I/O设备(device)。用来与外界交换信息，包括鼠标键盘显示器，包括磁盘驱动器（disk driver）或者简称disk。I/O设备通过控制器（controller）或者（adapter）与I/O bus连接。前者是设备主板上的芯片组，后者是一张插在主板插槽上的卡。
    3. 主存(main memory)。一个临时存储设备，<font color=#00ffff>在处理器执行程序时，用来存放程序和程序处理的数据</font>。物理上是由一组<font color=#00ffff>动态随机存取（访问）存储器（RAM)</font>构成。逻辑上是一个线性的字节数组，每个字节有其唯一的地址。
    4. 中央处理单元(CPU)，简称处理器(processor)。<font color=#00ffff>作用：解释或执行存储在主存中指令的引擎</font>。核心是大小为一个字的寄存器PC。还包括寄存器文件（register file）和算数/逻辑单元（ALU）。CPU使用了复杂的机制来加速机器指令的运行。我们区分处理器的指令集架构和处理器的微体系结构。
        1. 指令集架构(instruction set architecture):描述了每条指令应该有什么功能，较为抽象，第3章。
        2. 微体系结构(microarchitecture):描述了处理器实际上如何实现每条指令，较为具体，第4章。
4. 高速缓存存储器（cache memory）
    - 作用：存放处理器近期可能要用到的数据
    - 针对问题：处理器和主存之间速度的差异，连接寄存器文件（register file），连接bus直通主存
    - 硬件：使用<font color=#00ffff>静态随机存取（访问）存储器(SRAM)</font>
5. 存储器层次结构
    1. 思想：cache
    2. 具体层次：寄存器 -> L1 cache -> L2 cache -> L3 cache -> 主存 -> 本地二级存储（本地磁盘）-> 远程二级存储
6. 操作系统，xv6学习
7. 并发(concurrency) 和并行(parallelism)
8. 剩下的比较超纲
