---
title: 6.x - 小结与测试 - 运算符
alias: 6.x - 小结与测试 - 运算符
origin: /chapter-5-summary-and-quiz/
origin_title: "5.x — Chapter 5 summary and quiz"
time: 2021-6-28
type: translation
tags:
- summary
---


## 章节回顾

- 使用括号明确指定运算符的优先级，避免歧义。（[[6-1-Operator-precedence-and-associativity|6.1 - 运算符优先级和结合律]]）
- 算数运算符的行为和普通的数学运算符是一样的。（[[6-2-Arithmetic-operators|6.2 - 数学运算符]]）求模运算符(`%`)返回正数相除的余数（[[6-3-Modulus-and-Exponentiation|6.3 - 求模和指数运算]]）
- 自增自减操作符可以对一个变量进行递增和递减操作。尽量避免使用自增自减操作符的后缀形式（[[6-4-Increment-decrement-operators-and-side-effects|6.4 - 自增自减运算符及其副作用]]）
- 注意操作符的副作用，尤其是在函数参数求值时。在一个语句中，不要让副作用两次作用于一个变量[[6-4-Increment-decrement-operators-and-side-effects|6.4 - 自增自减运算符及其副作用]]）
- 逗号运算符可以将多个语句合并为一个。但是多个语句通常分开写会更好。（[[6-5-Comma-and-conditional-operators|6.5 - 逗号和条件运算符]]）
- 条件运算符可以构建一个**精简版**的 if 语句，但是并不要把它当做 if 语句的代替。只有当你关系它的结果时再使用（[[6-7-Relational-operators-and-floating-point-comparisons|6.7 - 关系运算符和浮点数比较]]）
- 关系运算符可以被用来对浮点数进行比较，但是要小心对浮点数应用**等于**和**不等于**（[[6-7-Relational-operators-and-floating-point-comparisons|6.7 - 关系运算符和浮点数比较]]）
- 使用逻辑运算符我们可以构建复合条件语句（[[6-8-Logical-operators|6.8 - 逻辑运算符]]）
