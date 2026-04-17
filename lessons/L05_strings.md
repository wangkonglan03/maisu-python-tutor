# 麦叔第5课：字符串——文字的处理

## 📖 课程目标

- 理解什么是字符串
- 掌握字符串的基本操作
- 学会字符串的切片和索引
- 了解实用的字符串函数

---

## 📝 什么是字符串？

**字符串** = 一串字符 = 一段文字

在Python里，字符串用**引号**包起来：

```python
# 单引号
名字 = '小明'

# 双引号
爱好 = "编程"

# 三引号（可以换行）
自我介绍 = """
大家好，
我叫小明，
很高兴认识你们！
"""
```

---

## 🔢 字符串的"门牌号"——索引

字符串里的每个字符都有一个"门牌号"（索引）：

```
字符串:  H   e   l   l   o
索引:     0   1   2   3   4
倒序索引: 0  -4  -3  -2  -1
```

```python
word = "Hello"

print(word[0])  # H（第一个字符）
print(word[1])  # e（第二个字符）
print(word[-1])  # o（最后一个字符）
print(word[-2])  # l（倒数第二个）
```

> 麦叔提示：**从0开始数！第一个不是1，是0！**

---

## ✂️ 字符串切片——取一部分

```python
word = "Hello World"

print(word[0:5])    # Hello（从0到4，不包括5）
print(word[6:11])   # World（从6到10）
print(word[6:])     # World（从6到结尾）
print(word[:5])     # Hello（从头到4）
print(word[:])      # Hello World（全部）
```

**语法：`字符串[开始:结束:步长]`**

---

## 🔗 字符串拼接——加法和乘法

### 加法：拼接字符串

```python
姓 = "张"
名 = "三"
全名 = 姓 + 名
print(全名)  # 张三

print("你好" + "，" + "小明！")  # 你好，小明！
```

### 乘法：重复字符串

```python
print("-" * 20)  # --------------------
print("Ha" * 3)   # HaHaHa
```

---

## 🔍 实用字符串函数

### 长度 `len()`

```python
name = "Python"
print(len(name))  # 6
```

### 大小写转换

```python
text = "Hello World"

print(text.upper())       # HELLO WORLD（全部大写）
print(text.lower())       # hello world（全部小写）
print(text.capitalize())  # Hello world（首字母大写）
print(text.title())       # Hello World（每个单词首字母大写）
```

### 判断开头结尾

```python
url = "https://www.baidu.com"

print(url.startswith("https"))  # True
print(url.endswith(".com"))     # True
```

### 替换

```python
text = "Hello World"
new_text = text.replace("World", "Python")
print(new_text)  # Hello Python
```

### 去除空白

```python
text = "   你好   "

print(text.strip())   # 你好（去除两边空格）
print(text.lstrip())  # 你好   （去除左边空格）
print(text.rstrip())  #   你好（去除右边空格）
```

### 分割

```python
sentence = "苹果,香蕉,橙子,葡萄"

fruits = sentence.split(",")
print(fruits)  # ['苹果', '香蕉', '橙子', '葡萄']
```

### 连接

```python
fruits = ['苹果', '香蕉', '橙子']
result = "、".join(fruits)
print(result)  # 苹果、香蕉、橙子
```

---

## 🔍 查找子串

```python
text = "Hello, 你好, World"

print("Hello" in text)     # True（在不在里面）
print(text.find("你好"))    # 7（返回位置，没找到返回-1）
print(text.count("o"))     # 2（出现次数）
```

---

## ❌ 常见错误

### 错误：字符串和数字直接相加

```python
# ❌ 错误
age = 18
print("我" + age + "岁")  # 报错！

# ✅ 正确
age = 18
print("我" + str(age) + "岁")  # 我18岁
```

---

## 💱 综合例子：个人信息卡片

```python
姓名 = "张三"
城市 = "北京"
年龄 = 25
职业 = "程序员"

# 基本信息
print("=== " + 姓名 + "的个人信息 ===")
print("姓名：" + 姓名)
print("城市：" + 城市)
print("年龄：" + str(年龄) + "岁")

# 自我介绍
intro = f"我是{姓名}，住在{城市}，今年{年龄}岁，是一名{职业}。"
print(intro)

# 统计
print(f"姓名的长度：{len(姓名)}个字")
print(f"职业用大写：{职业.upper()}")
```

---

## 📝 今日要点

```
✅ 字符串 = 用引号包起来的文字
✅ 索引从0开始：word[0]是第一个字符
✅ 切片：word[开始:结束]（不包含结束）
✅ 拼接用 +，重复用 *
✅ len()长度，upper()/lower()大小写
✅ split()分割，join()连接
✅ 数字和字符串不能直接加，要用str()转换
```

---

## 🏋️ 动手练习

### 练习1：字符串操作
```python
text = "Python是最流行的编程语言"
# 1. 输出text的长度
# 2. 输出第一个字符
# 3. 输出"最流行"这三个字
# 4. 把它全部大写输出
```

### 练习2：个人信息
把以下内容合并成一句话：
```
a = "我是"
b = "小明"
c = "，我喜欢"
d = "编程"
e = "！"
```

### 练习3：电话号码脱敏
```python
phone = "13812345678"
# 把中间4位变成****
# 提示：用到切片和拼接
```

### 练习4（挑战）：统计字符
输入一句话，统计里面有多少个"a"（不区分大小写）

---

## 🎖️ 本课徽章

完成练习1-2：**🐣 字符串侠**  
完成练习3-4：额外获得 ⭐ 挑战者徽章

---

## 📌 下节课预告

- 布尔值（True/False）
- 比较运算（大于、小于、等于）
- 条件判断 if/else

准备好了就告诉麦叔！👨‍🏫
