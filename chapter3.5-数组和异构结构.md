# 数组
1. 计算公式
    - A + L(C * i + j)
    - 所以使用“比例变址寻址”，详见3.1
2. 编写规范
``` C
// 定长：N在编译时已确定，变长：N在运行时才确定
// 定长数组
#define N 16
typedef int fix_matrix[N][N]
void func(fix_matrix A);

// 变长数组
void func(int n, int A[n][n]);
```
3. 汇编优化
    - 略
-------------------
# struct，union
1. 内存分配不多说
2. 最佳代码
``` C
typedef enum {N_LEAF, N_INTERNAL} nodetype_t;

struct node_t{
    nodetype_t type;
    union{
        struct{
            struct node_t * left;
            struct node_t * left;
        } internal;
        double data[2];
    } info;
}
```
3. union 骚操作
    - long u = long(d); // double -> long, 强制转换
    - 使用union可以进行位级转换
--------------------
# 对齐
1. 跳转表的对齐
    - .align 8
    - jump指令都是8的偏移
2. struct 对齐
    - 从元素角度，若大小为K，则应该 addr%K = 0
    - 从整体角度，struct整体应该 "最大内部元素" 对齐 (形成数组)
-------------------------
# 补充
1. 跳转表
    - switch中使用，jump指令使用了*，是指令地址。对应C中的&&
2. 函数指针
``` C
int a;
int fun(int x, int *p);
int (*fp)(int x, int * p);
int res = fp(1, &a);
```

