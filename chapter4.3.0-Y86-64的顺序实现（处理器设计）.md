## 将指令分阶段
1. 取址（fetch）
   - 取指令第一个字节，分icode和ifun
   - 指明rA，rB
   - 取出valC（先取出，用不用另说）
   - 计算valP
2. 译码（decode）
   - 根据rA，rB得到valA，valB
3. 执行（execute）
   - 根据ifun，在ALU中计算，得到valE
   - 有些会计算Cnd信号，jxx和comv
4. 访存（memory）
   - 写入或读出，读出为valM
5. 写回（write back）
   - 写回寄存器
   - 最多可以写两个结果到寄存器文件（valE和valM）（pop指令就写两个）
6. 更新PC（update PC）
   - 根据valP设置PC
--------
## 为什么要设计，怎么描述设计
- 希望使用最少的硬件（一个ALU）实现所有的指令
- 用HCL描述