# 麦叔第9课：while循环——满足条件就继续

## 📖 课程目标

- 理解 while 循环的原理
- 掌握 while 和 for 的区别
- 学会用 while 写无限循环和退出
- 能用 while 解决实际问题

---

## 🔄 while vs for

| | for | while |
|---|---|---|
| 什么时候用 | 知道要循环几次 | 不知道要循环几次 |
| 结束条件 | 数完就停 | 条件不满足就停 |
| 例子 | 打印1-100 | 猜数字直到猜对 |

---

## 🏠 while 的基本语法

```python
while 条件:
    重复做的事
```

**只要条件成立，就一直做。**

```python
count = 0
while count < 5:
    print("第", count, "次")
    count = count + 1  # 记得更新计数器！
```

**输出：**
```
第 0 次
第 1 次
第 2 次
第 3 次
第 4 次
```

> ⚠️ **重要：如果不更新计数器，while会永远运行下去（死循环）！**

---

## ⌨️ 实用例子：菜单循环

```python
while True:  # 永远循环
    print("=== 麦叔计算器 ===")
    print("1. 加法")
    print("2. 减法")
    print("3. 退出")
    
    choice = input("请选择：")
    
    if choice == "3":
        print("再见！")
        break  # 退出循环
    elif choice == "1":
        a = int(input("第一个数："))
        b = int(input("第二个数："))
        print("结果：", a + b)
    elif choice == "2":
        a = int(input("第一个数："))
        b = int(input("第二个数："))
        print("结果：", a - b)
```

---

## 🎯 猜数字游戏（while版）

```python
import random

答案 = random.randint(1, 100)
猜测次数 = 0

print("=== 猜数字游戏 ===")

while True:
    猜测 = int(input("猜一个1-100的数字："))
    猜测次数 = 猜测次数 + 1
    
    if 猜测 == 答案:
        print(f"🎉 恭喜你！用了{猜测次数}次猜对！")
        break  # 猜对了，退出
    elif 猜测 < 答案:
        print("太小了")
    else:
        print("太大了")
```

---

## 🔢 while 用于计数

```python
# 倒计时
countdown = 10
while countdown > 0:
    print(countdown)
    countdown = countdown - 1
print("发射！🚀")
```

**输出：**
```
10
9
8
7
6
5
4
3
2
1
发射！🚀
```

---

## ⚠️ 死循环的例子

```python
# ❌ 错误示范：忘了更新计数器
count = 0
while count < 5:
    print(count)
    # 忘了 count = count + 1
    # 这个程序会永远打印0！
```

```python
# ✅ 正确做法：记得更新
count = 0
while count < 5:
    print(count)
    count = count + 1  # 每次加1
```

---

## 💡 while + flag（标志变量）

```python
游戏继续 = True

while 游戏继续:
    行动 = input("做什么？（输入q退出）")
    
    if 行动 == "q":
        游戏继续 = False  # 或者 break
        print("游戏结束！")
    else:
        print("做了", 行动)
```

---

## 📝 今日要点

```
✅ while 条件:  # 条件成立就一直做
✅ for 适合知道次数，while 适合不知道次数
✅ 一定要更新计数器，避免死循环
✅ break 可以提前退出 while 循环
✅ while True: 表示永远循环，配合 break 使用
✅ 记得：死循环是while最常见的错误！
```

---

## 🏋️ 动手练习

### 练习1：1+2+3...直到和超过100
用while计算：1+2+3+...，直到和超过100，输出加到了多少

```python
总和 = 0
数字 = 1
while 总和 <= 100:
    总和 = 总和 + 数字
    数字 = 数字 + 1
print("加到了", 数字-1, "总和是", 总和)
```

### 练习2：密码验证
密码是"python"，一直问直到输入正确

```python
密码 = "python"
while True:
    输入的密码 = input("请输入密码：")
    if 输入的密码 == 密码:
        print("正确！登录成功！")
        break
    else:
        print("密码错误，重新输入")
```

### 练习3：ATM取款模拟
余额1000元，循环取钱直到余额不足或用户退出

```python
余额 = 1000
while 余额 > 0:
    print(f"当前余额：{余额}元")
    取款 = int(input("取款金额（输入0退出）："))
    if 取款 == 0:
        print("退出")
        break
    elif 取款 > 余额:
        print("余额不足！")
    else:
        余额 = 余额 - 取款
        print("取款成功！")
print("交易结束")
```

### 练习4（挑战）：石头剪刀布
用while实现一个可以无限玩的石头剪刀布游戏，统计胜率

---

## 🎖️ 本课徽章

完成练习1-2：**🔄 循环战士**  
完成练习3-4：额外获得 ⭐ 挑战者徽章

---

## 📌 下节课预告

- 列表——装很多东西的盒子
- 列表的增删改查
- 列表的常用函数

准备好了就告诉麦叔！👨‍🏫
