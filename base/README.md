# 基础准备知识
一些数据结构和算法中经常使用到的基本概念和名词


## 复杂度

- 大O符号表达式(Big O graphs)：O(f(n)) 
- f(n)：表达算法的增长趋势
- O：表示复杂度正比例关系
- 复杂度量级：(由上到下复杂度依次增加)
    - 常数阶：O(1)
    - 对数阶：O(log n)
    - 线性阶：O(n)
    - 线性对数阶：O(n log n)
    - 平方阶：O(n^2)
    - 立方阶：O(n^3)
    - K次方阶：O(n^k)
    - 指数阶：O(2^n)
    - 阶层阶：O(n!)

- 大O符号表达式的国外汇总: [https://www.bigocheatsheet.com/](https://www.bigocheatsheet.com/)
![Big O graphs](../assets/big-o-graph.png)

### 时间复杂度

- T(n) = O(f(n)): 表达算法执行时间的增长趋

### 空间复杂度

- S(n) = O(f(n)): 表达算法所占空间的增长趋势

### 常见的复杂度

**常数阶O(1)**

```javascript
const a = 1; // 执行1次，a空间占用1个
const b = 2; // 执行1次，b空间占用1个
const c = a + b; // 执行1次，c空间占用1个
console.log(c); // 执行一次，不占用空间
```

- 时间复杂度：T(n) = O(1), 每行程序执行都为单独执行1次，总计4次，O(1)代表总体常数函数，可以不用O(4)表示
- 空间复杂度：S(n) = O(1), a/b/c变量不随着执行程序的变化而变化

**对数阶O(logn)**

```javascript
const temp = []; // 执行一次，temp空间占用0字节
for (let i = 1; i < n; i = i * 2) { // 执行 log n 次（反向推理：极限2 ^ x = n，则x = log n，底数为2可忽略）
    temp.push(i); // 由于执行log n次，数组temp数据也占用log n个字节空间
    console.log(i);
}
```

- 时间复杂度：T(n) = O(log n)
    - i、n 与 循环的执行次数 的数学关系枚举：2, 4, 8, 16 ... 2^x >= n , x ≈ log2 n，x表示执行的次数，发现底数(2)越大，执行次数越少
- 空间复杂度：S(n) = O(log n)
    - 推理过程如上述类似


**线性阶O(n)**

```javascript
const temp = new Array(n); // 执行一次，空间占用n个字节
for (let i = 0; i < n; i ++) { // 执行n次
    temp.push(i); // 执行n次
}
```

- 时间复杂度：T(n) = O(n)
- 空间复杂度：S(n) = O(n)