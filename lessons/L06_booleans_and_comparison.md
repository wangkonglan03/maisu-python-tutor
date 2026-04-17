# 麦叔第6课：布尔值和比较——判断对错

## 📖 课程目标

- 理解布尔值（True/False）
- 掌握比较运算符
- 理解逻辑运算（and/or/not）
- 学会用bool()转换

---

## ✅ 布尔值是什么？

布尔值只有**两个可能**：

| 值 | 意思 | 中文 |
|----|------|------|
| `True` | 对/真 | 是 |
| `False` | 错/假 | 否 |

```python
是学生 = True
有作业 = False

print(是学生)   # True
print(有作业)   # False
```

> 麦叔说："布尔值就像开关，只有两种状态：开（True）或关（False）。"

---

## 🔍 比较运算——比大小

比较运算的结果就是布尔值：

```python
a = 10
b = 5

print(a > b)    # True（10大于5吗？是的）
print(a < b)    # False（10小于5吗？不是）
print(a >= b)   # True（10大于等于5）
print(a <= b)   # False（10小于等于5）
print(a == b)   # False（10等于5吗？不是）
print(a != b)   # True（10不等于5吗？是的）
```

### 麦叔口诀

```
大于  >
小于  <
大于等于  >=
小于等于  <=
等于    == （注意是两个等号！）
不等于  !=
```

> ⚠️ **注意**：一个等号 `=` 是赋值，两个等号 `==` 是比较！

---

## 🔗 逻辑运算——组合判断

### `and` —— 并且

两个都要满足才是True

```python
print(True and True)    # True
print(True and False)   # False
print(False and False)  # False

# 例子：18岁以上 且 有驾照 才能开车
年龄 = 20
有驾照 = True
可以开车 = 年龄 >= 18 and 有驾照 == True
print(可以开车)  # True
```

### `or` —— 或者

满足一个就行

```python
print(True or True)    # True
print(True or False)   # True
print(False or False)  # False

# 例子：会员 或 付费用户 可以观看
是会员 = False
已付费 = True
可以观看 = 是会员 or 已付费
print(可以观看)  # True
```

### `not` —— 取反

True变False，False变True

```python
print(not True)   # False
print(not False)  # True

是学生 = True
不是学生 = not 是学生
print(不是学生)  # False
```

---

## 🎯 组合使用

```python
年龄 = 25
工资 = 8000
信用分 = 750

# 可以贷款吗？
# 条件：25-60岁 且 工资>5000 或 信用分>700
可以贷款 = (25 <= 年龄 <= 60) and (工资 > 5000 or 信用分 > 700)
print(可以贷款)  # True
```

---

## 🔄 类型转换——变成布尔值

### 哪些是True，哪些是False？

```python
print(bool(1))        # True（非零数字）
print(bool(0))        # False（零）
print(bool("hello"))  # True（非空字符串）
print(bool(""))       # False（空字符串）
print(bool([]))       # False（空列表）
print(bool(None))     # False（空值）
```

> 麦叔记忆法：**"0、空、None都是False，其他都是True"**

---

## 💡 实用的判断技巧

### 判断年份是否闰年

```python
年份 = 2024

# 闰年条件：能被4整除但不能被100整除，或者能被400整除
是闰年 = (年份 % 4 == 0 and 年份 % 100 != 0) or (年份 % 400 == 0)
print(年份, "是闰年吗？", 是闰年)  # True
```

### 判断是否在范围内

```python
分数 = 85

# 及格：60-100分
及格 = 60 <= 分数 <= 100
print("及格了吗？", 及格)  # True
```

---

## 📝 今日要点

```
✅ 布尔值只有两个：True（真）和 False（假）
✅ 比较运算：> < >= <= == !=（结果是布尔值）
✅ 逻辑运算：
   - and：两边都要True才是True
   - or：一边是True就是True
   - not：取反，True变False
✅ 类型转换：bool()可以把其他类型变成布尔值
✅ 记住："0、空、None都是False，其他都是True"
```

---

## 🏋️ 动手练习

### 练习1：判断对错
```python
# 下面这些判断，答案是什么？
print(10 > 5)
print(7 == 7)
print(3 != 3)
print("hello" == "hello")
```

### 练习2：组合判断
```python
年龄 = 20
是学生 = True

# 判断：是否是可以申请学生票的人（18-25岁之间的学生）
# 你的代码：
```

### 练习3：复杂判断
```python
账号 = "admin"
密码 = "123456"

# 判断：账号是"admin" 且 密码是"123456"
# 你的代码：
```

### 练习4：逻辑运算
```python
a = True
b = False

# 写出下面每个的结果
print(a and b)
print(a or b)
print(not a)
print(not b and a)
```

---

## 🎖️ 本课徽章

完成练习1-2：**🔍 判断高手**  
完成练习3-4：额外获得 ⭐ 挑战者徽章

---

## 📌 下节课预告

- if 语句——如果...那么...
- else 语句——否则...
- 多重判断 elif
- 嵌套判断

准备好进入下一个重磅内容了！告诉麦叔！👨‍🏫
