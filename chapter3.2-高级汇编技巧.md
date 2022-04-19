### 条件分支
1. 条件控制实现
``` c
if(!test-expr)
  goto L2
 L1:
   balabala
   ret
 L2:
   balabala
   ret
```
2. 条件传送（cmov）实现
``` c
A-expr = ...
B-expr = ...
if(!test-expr) A = B
return A
```
3. tips
  1. je 和 jz 一个效果
  2. 条件传送比条件控制效率高，但要求也高
------
# 循环
-------
### do-while
``` c
loop:
  body-statement
  t = test-expr;
  if(t) goto loop;
```
------------
### while
1. 第一种方法：jump to middle
```c
// 相比do-while，多了第一个goto
goto test
loop:
  body-statement
test:
  t = test-expr;
  if(t) goto-loop;
```

2. 第二种方法：guarded do
``` c
  t = test-expr
  if(!t) goto done
loop:
  body-statement
  t = test-expr
  if(t) goto loop
done:
  ret
```
3. 比较
  - 第二种方法，对处理器友好，效率较高
  - 一般 -O1 就是第二种方法
4. 为什么更好
  - 当编译器认为初始test-expr一定满足时，编译器会省略掉这一步
------
### for
```c
for(init-expr; test-expr; update-expr)
  body-statement
```
- 等价while(一种例外，continue)
``` c
init-expr;
while(test-expr){
  body-statement;
  update-expr;
}
```
- 翻译为jump to middle和 guarded do时，参考while
------
