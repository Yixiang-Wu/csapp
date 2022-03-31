调试源代码
0. gcc -g 才能调试
1. n 不进函数体的单步
2. s 进入函数体的单步
3. b [行数]  打上断点
4. continue 到达下一个断点
5. run 开始
6. 糖 //回车，表示和上次一样
7. k // kill debug
8. info b 看断点


调试汇编
1. disassemble phase_1
2. info register esi
3. print (char*) 0x402400
4. print (char) *0x402400
5. stepi
6. nexti