## disjunctions(inclusive or)包含性的或

就是或的关系,p or q,

denoted by p ∨ q

(至少一个命题为真,可以两个都真)



## exclusive or   排他性的或

恰好一个命题为真,(不能两个都真)

异或,记作“p XOR q”, denoted by “p ⊕ q”



*In mathematics, we don't use 'exclusive or' very often. Most of the time, or means inclusive or.*
（在数学中，我们不常用“异或”。大多数情况下，“或”指的是包含性的或。）



## 恒等律

### 1. `p ∧ T` （p 与 True 的合取）

- 合取（AND）要求两边同时为真，结果才为真。
- 如果 `p = T`，则 `T ∧ T = T`
- 如果 `p = F`，则 `F ∧ T = F`
- 结果总是 **等于 p 本身**。

**答案：** `p ∧ T ≡ p`

------

### 2. `p ∨ T` （p 与 True 的析取）

- 析取（OR）只要有一边为真，结果就为真。
- 因为右边已经是 `T`，无论 `p` 是什么，结果都是 `T`。

**答案：** `p ∨ T ≡ T` （恒真）

------

### 3. `p ∧ F` （p 与 False 的合取）

- 合取要求两边同时为真。右边是 `F`，所以结果永远是 `F`。

**答案：** `p ∧ F ≡ F` （恒假）

------

### 4. `p ∨ F` （p 与 False 的析取）

- 析取只要有一边为真就为真。右边是 `F`，所以结果完全由 `p` 决定：
  若 `p = T` 则 `T ∨ F = T`；若 `p = F` 则 `F ∨ F = F`。

**答案：** `p ∨ F ≡ p`





## 条件 conditional statement

p →q is the statement “If p, then q”.

有前必有后,

无前未必无后



### 1. p implies q（p 蕴含 q）

- 最直接的表达，就是“如果 p 为真，那么 q 也必须为真”。

### 2. p only if q（p 仅当 q）

- 这是一个容易混淆的表达。
  “p only if q” 意思是：**如果 p 发生了，那么 q 一定已经发生了**。也就是说，p 为真的前提是 q 必须为真。这等价于 p→qp→q。
  **注意**：“p only if q” ≠ “p if q”（后者是 q→pq→p）。



### 3. q if p（q 如果 p）

- 这是最直接的“如果 p，则 q”的另一种语序。

### 4. q whenever p（每当 p，则 q）

- 强调时间或条件上的伴随关系：只要 p 出现，q 就会伴随出现。

### 5. qq follows from pp（q 由 p 得出）

- 逻辑推导关系：从 p 可以推出 q。



### 6. pp is sufficient for qq（p 是 q 的充分条件）

- 充分条件：有 p 就足够保证 q 成立。即 p→q。

### 7. qq is necessary for pp（q 是 p 的必要条件）

- 必要条件：如果没有 q，就不可能有 p。即 p→q等价于 ¬q→¬p，所以 q 是 p 的必要条件。

### 8. ¬p or q（非 p 或 q）

- 这是逻辑等价式：p→q≡¬p∨q
  意思是：要么 p 为假，要么 q 为真。

### 9. q unless ¬p（q 除非 非 p）

- “除非”表示一种例外条件：除非 p 不成立，否则 q 成立。也就是说，如果 p 成立，则 q 成立；如果 p 不成立（即 ¬p 成立），则 q 不一定。这正好是 p→q。



## 常见易混淆点

- **“p only if q”** 不要和 **“p if q”** 搞混：
  - “p if q” = q→p
  - “p only if q” = p→q
- **充分条件 vs 必要条件**：
  - pp 是 qq 的充分条件：p→q
  - qq 是 pp 的必要条件：同样 p→q（因为 q 是必要条件意味着没有 q 就没有 p）







## 一个非常重要的**逻辑等价式**：



**<u>p→q≡¬p∨q</u>**

### 这个等价式有什么用？

1. **简化逻辑表达式**：可以把条件语句转换成“或”和“非”的形式，有时更容易处理。
2. **证明其他等价关系**：比如逆否命题 ¬q→¬p¬q→¬p 也可以用这个式子推导出来。
3. **编程中的应用**：在代码中，`if (p) then q` 有时可以写成 `(!p) || q`。





## 逆命题,否命题,逆否命题

### 1. 三个概念的定义（以原命题 p→q 为基础）

|   名称   |      英文      | 形式  |      与原命题的关系      |
| :------: | :------------: | :---: | :----------------------: |
|  原命题  |    Original    |  p→q  |            —             |
|  逆命题  |    Converse    |  q→p  |        不一定等价        |
|  否命题  |    Inverse     | ¬p→¬q |        不一定等价        |
| 逆否命题 | Contrapositive | ¬q→¬p | **逻辑等价**（同真同假） |

**重要结论**：原命题与逆否命题等价，逆命题与否命题等价



### 2. 例子分析

> **原英文句子**：*You die unless you eat.*
> 翻译：你死，除非你吃饭。

这句话是一个条件语句，但用了“unless”（除非）的结构。我们要先把它转换成标准的“if-then”形式。

#### 步骤1：理解“unless”

在逻辑中，“q unless ¬p” 等价于 p→qp→q（见第18页最后一条）。
更直接地说：“A unless B” 通常理解为 **如果非B，则A**。
或者另一种等价形式：**如果 A 不发生，则 B 发生**。

这里：“You die unless you eat.”

- 设 pp：你吃饭（you eat）
- 设 qq：你死（you die）

“unless” 表示：如果你不吃饭，你就会死。
所以 if-then 形式是：**如果你不吃饭，那么你会死**。

即：¬p→q¬p→q。

> 注意：有人可能会设成 p→¬qp→¬q 吗？我们按标准逻辑转换：
> “A unless B” 通常翻译成：如果非 B，则 A。
> 所以 “q unless p” 就是 ¬p→q¬p→q。

因此本例中：

- 设 pp：你吃饭
- qq：你死
- 原句 = qq unless pp = ¬p→q¬p→q

但课件的例子可能期望另一种常见等价形式：“You die unless you eat” 也等于 “If you do not eat, then you die” = ¬p→q¬p→q。
然后题目要求写出“if-then form”，就是 ¬p→q¬p→q。

接下来要求写出它的 **converse, inverse, contrapositive**，但注意：这些概念通常是针对一个标准形式的条件语句 p→qp→q 定义的。这里原句的 if-then 形式是 ¬p→q¬p→q，所以我们需要把这个当作“原命题”来处理。

------

### 3. 写出例子的各个形式

设：

- 原命题（if-then 形式）：**如果你不吃饭，那么你会死**。
  符号：¬p→q¬p→q，其中 pp = 你吃饭，qq = 你死。

现在按定义写出：

#### 逆命题（Converse）

交换前提和结论：q→¬pq→¬p
中文：**如果你会死，那么你不吃饭**。

#### 否命题（Inverse）

对前提和结论分别否定：原命题是 ¬p→q¬p→q，否定前提得 ¬(¬p)=p¬(¬p)=p，否定结论得 ¬q¬q，所以得到 p→¬qp→¬q
中文：**如果你吃饭，那么你不会死**。

#### 逆否命题（Contrapositive）

交换并否定原命题：原命题 ¬p→q¬p→q 的逆否是 ¬q→¬(¬p)=¬q→p¬q→¬(¬p)=¬q→p
中文：**如果你不会死，那么你吃饭了**。







## Biconditional statement

 The biconditional statement
p ↔q is the proposition “p if and only if q”.





## 逻辑运算符的优先级

1. ¬（非）—— 最高优先级
2. ∧（与）和 ∨（或）—— 次高优先级
3. →（蕴含）和 ↔（双向蕴含）—— 最低优先级

### 例子解析

#### 例子1：¬p ∧ q 的含义是什么？

根据优先级，¬ 先于 ∧，所以：

- 先计算 ¬p
- 再将结果与 q 做 ∧

即：**(¬p) ∧ q**
意思是“非 p 且 q”，而不是 ¬(p ∧ q)（后者表示“并非 p 且 q 同时成立”）。

举例：

- 设 p 为真，q 为真：
  ¬p 为假，所以 (¬p) ∧ q = 假 ∧ 真 = 假
  如果是 ¬(p ∧ q) = ¬(真 ∧ 真) = ¬真 = 假（巧合相同，但逻辑意义不同）

#### 例子2：最好将 p ∨ q ∧ r 写成什么形式？

因为 ∧ 和 ∨ 优先级相同，p ∨ q ∧ r 有歧义：

- 可能是 (p ∨ q) ∧ r
- 也可能是 p ∨ (q ∧ r)

为避免歧义，应该**加上括号**明确顺序。通常在实际中，如果没括号，默认从左到右结合，但不同教材可能不同。所以“更好写成”的意思是：用括号明确你的意图。

比如：

- 如果你想表达 (p ∨ q) ∧ r，就写成那样。
- 如果你想表达 p ∨ (q ∧ r)，就写成那样。

课件这里没有指定正确答案，只是提醒：**当优先级相同时，用括号消除歧义**。

#### 例子3：p → q ∨ r 的含义是什么？

根据优先级，→ 低于 ∨，所以先计算 ∨：

- q ∨ r 先结合
- 然后 p → (q ∨ r)

即：**如果 p 为真，则 q 或 r 至少一个为真**。
而不是 (p → q) ∨ r（后者表示“p 蕴含 q”或者 r 成立）。



## 重言式

A compound proposition that is always true/false, no matter what the truth values of the propositional variables are that occur in it, is called a tautology/contradiction

一个复合命题，无论其中出现的命题变量的真值如何，其结果始终为真/假，这种命题被称为重言式/矛盾式。

- **重言式（tautology）**：一个复合命题无论其中的命题变元取真还是假，结果**永远为真**。

#### 例子1：p∨¬p

- 这个叫**排中律**。
- 真值表：
  - 若 p=T，则 ¬p=F，T∨F=T。
  - 若 p=F，则 ¬p=T，F∨T=T。
- **结论**：永远为真 → **重言式**





## 矛盾式

- **矛盾式（contradiction）**：一个复合命题无论其中的命题变元取真还是假，结果**永远为假**。

#### 例子2：p∧¬p

- 这个叫**矛盾律**。
- 真值表：
  - 若 p=T，则 ¬p=F，T∧F=F。
  - 若 p=F，则 ¬p=T，F∧T=F。
- **结论**：永远为假 → **矛盾式**





## 逻辑等价

Two compound propositions P and Q are called logical equivalent if the biconditional statement P ↔ Q is always a tautology (regardless of P and Q are true or not), in which case we denote “P ≡Q”, or “P =Q”, or sometimes “P ⇔ Q”. Basically, it means that P and Q always have the same truth values in all cases.

### 例子

你之前已经见过一个等价：

p→q  ≡  ¬p∨q

验证：真值表两列完全相同。



## 交换律结合律分配律

![77606464018](C:\Users\叶健钦\AppData\Local\Temp\1776064640184.png)