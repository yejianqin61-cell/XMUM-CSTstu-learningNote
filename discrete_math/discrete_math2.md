# Predicates 谓词(命题函数)

**Definition**
A propositional function, or predicate, is a proposition-valued function
P:a domain D→ a proposition.

命题函数，或称谓词，是一个从定义域 D 映射到命题的函数。

**例子：** A(x)：计算机 x 正受到黑客攻击。

A(1):计算机1正受到黑客攻击

A(2):.......

........

**例子：** P(x):(x>3)，其中 x 的定义域为实数。问 P(3.001) 和 P(2.999) 的真值是什么？

**例子：** Q(x,y):(x=y+3)，其中 x,yx,y 的定义域为整数。问 Q(1,2) 和 Q(7834,7831) 的真值是什么？



- **<u>谓词不是命题，只有代入具体值后才变成命题（有真值）。</u>**


- Q(1,2) 为假（1=2+3? 不成立）,Q(7834,7831) 为真（7834=7831+3? 成立）



# 全称量词



The universal quantification of P(x) is the statement
"P(x) for all values of x (in a domain)"
or just "for all x, P(x)", and denoted by ∀x,P(x).

P(x) 的全称量化是指语句：
“对于定义域中的所有 x，P(x) 成立”
或简写为“对所有 x，P(x)”，记作 ∀x,P(x)。





**例子：**

- 对所有 x 在定义域 (3,∞)中，P(x):(x>3) 为真。
- 对所有 x 在定义域 [3,∞) 中，P(x):(x>3) 为假（因为 x=3 时不大于 3）。



## 全称量词的反例



**Definition** Given " ∀x,P(x) ", If there is at least one c in D such that P(c) is not true, then we say that c is a counterexample to " ∀x,P(x)".



给定 “∀x,P(x)”，如果存在至少一个c∈D 使得 P(c) 不成立，则称 c 是该全称量词语句的反例。

**例子：**

- x=3 是 “对所有 x∈[3,∞)，P(x):x>3” 的反例。
- “对所有 x∈(5,∞)，P(x):x>3” 没有反例（所有 x>5 都大于 3）。



# 存在量词



**<u>有时用 ∃! 表示存在唯一的 x 使 P(x) 成立。</u>**

**例子：**

- “若 x 在 [2,∞) 中，则 ∃!x,P(x):(x≤2)” 为真（只有 x=2 满足）。
- “若 x 在 [2,∞) 中，则 ∃!x,P(x):(x>4)” 为假（不止一个）。

**例子：** 令 Q(x)=(x=x+1)，则 “∃x,Q(x)” 为假。

**解析：**
存在量词只需至少一个；唯一存在量词要求恰好一个。



# 量词和逻辑连接词的关系



有限定义域上的量词。

D={1,2,…,n}

当 D 有限时，∧/∨ 与 ∀/∃ 的关系：

- “∀x ∈ D，P(x)” 等价于 P(1)∧P(2)∧⋯∧P(n)
- “∃x ∈ D，P(x)” 等价于 P(1)∨P(2)∨⋯∨P(n)

**注意：**
如果 D 是无限的（如实数区间），就不能用 ∧/∨ 来等价表示，只能用 ∀/∃。



# 逻辑运算符的优先级

- 最高：∀ 和 ∃
- 其次：¬
- 再其次：∧ 和 ∨
- 最低：→ 和 ↔

例子：∀x,P(x)∨Q(x) 意思是 (∀x,P(x))∨Q(x)？不对——它意思是

∀x,(P(x)∨Q(x))。

**解析：**
量词优先级高于逻辑连接词，但通常建议加括号避免歧义。



# 量词的两个重要分配律

Some equivalences
∀x(P(x)∧Q(x))≡∀xP(x)∧∀xQ(x)
∃x(P(x)∨Q(x))≡∃xP(x)∨∃xQ(x)

Think of the finite domain case.
Remark. It applies to the infinite domain case too.

**中文翻译：**
一些等价关系

- 全称量词对 ∧ 可分配
- 存在量词对 ∨ 可分配

想想有限定义域的情况就明白了。
注意：这也适用于无限定义域。



# 量词的一些不等价关系



Some non-equivalences

∃x(P(x)∧Q(x))≢ ∃xP(x)∧∃xQ(x)

∀x(P(x)∨Q(x))≢∀xP(x)∨∀xQ(x)

Hint: It is enough to think of x in {1,2}.

**中文翻译：**
一些不等价关系

- 存在量词不能分配到 ∧ 上
- 全称量词不能分配到 ∨ 上



# 量词里的德摩根定律

De Morgan’s laws for quantifiers.
¬(∀xP(x))≡∃x¬P(x)
¬(∃xP(x))≡∀x¬P(x)

Again, think of the finite domain case.
Remark. It applies to the infinite domain case too.



# 嵌套量词

1.5 嵌套量词

**例子：**
x 在 A 大学的学生中，y 在 B 大学的学生中（A ≠ B），
F(x,y)：x 和 y 是朋友。

- ∀x∀yF(x,y)：A 大学的每一个学生与 B 大学的每一个学生都是朋友。
- ∃x∃yF(x,y)：存在 A 大学的一个学生与 B 大学的一个学生是朋友。

**例子：**
对所有实数 x, y，x+y=y+x（加法交换律）。



The Order of Quantifiers

∀x∀y,P(x,y)≡∀y∀x,P(x,y),

∃x∃y,P(x,y)≡∃y∃x,P(x,y)

but

∀x,∃y,P(x,y)≢ ∃y,∀x,P(x,y).

- 同种量词交换顺序等价。
- 不同种量词交换顺序不等价。

### 顺序很重要

**xample.**
∀x∃y(x+y=0) (True: for any x, take y = -x)
∃x∀y(x+y=0) (False: no single x works for all y)

**中文翻译：**
记住：当 ∀ 和∃ 嵌套在一起时，顺序很重要。