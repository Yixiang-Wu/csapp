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
