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
### 循环
1. do-while
``` c
loop:
  body-statement
  t = test-expr;
  if(t) goto loop;
```

2. while
```c
// 相比do-while，多了第一个goto
goto test
loop:
  body-statement
test:
  t = test-expr;
  if(t) goto-loop;
```
