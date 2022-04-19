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
