# 麦叔第2课：Python是什么？

## 📖 课程目标

- 理解Python是什么
- 知道怎么在电脑上安装Python
- 准备好编程环境
- 写出你的第一行代码

---

## 🐍 Python的诞生

Python的创造者叫**吉多·范罗苏姆（Guido van Rossum）**，荷兰人。

1991年，他创造了这门语言。

**为什么叫Python？**
不是因为蛇，而是因为——他喜欢一个英国喜剧团体叫**Monty Python**。所以用"Python"命名。

---

## 🎯 Python能做什么？

```
🌐 网站开发      → 你每天刷的网站可能就用Python写的
📊 数据分析      → 处理大量数据，做图表
🤖 人工智能      → 机器学习、聊天机器人
🎮 游戏开发      → 简单的小游戏
📱 自动化工具    → 帮你自动处理重复的工作
🌍 爬虫          → 自动获取网络上的信息
```

> 麦叔说："Python就是编程界的瑞士军刀！"

---

## 💻 怎么安装Python？

### 第一步：去官网下载

打开浏览器，访问：
```
www.python.org
```

点击 **Downloads（下载）**，会自动检测你的电脑系统，给出推荐的下载按钮。

### 第二步：安装

下载好后，双击安装文件。

⚠️ **重要**：安装时一定要勾选 **"Add Python to PATH"**（把Python加到系统路径）

### 第三步：验证安装

打开命令提示符（Windows按 Win+R，输入 `cmd`，回车），输入：

```
python --version
```

如果看到 `Python 3.x.x`，说明安装成功了！

---

## 🎉 你的第一个程序：Hello World

"Hello World" 是编程界的传统——每个学编程的人，第一个程序都是输出 "Hello World"。

### 打开Python

Windows用户：按 Win+R，输入 `python`，回车

你会看到这样的界面：
```
Python 3.x.x
Type "help" for more information.
>>>
```

那个 `>>>` 叫**提示符**，意思是"我在等你输入命令"。

### 打字

在 `>>>` 后面输入：

```python
print("Hello World")
```

按回车！

---

## 🔍 逐行解析

```python
print("Hello World")
```

| 部分 | 意思 |
|------|------|
| `print` | 打印，输出 |
| `()` | 里面放要输出的内容 |
| `"Hello World"` | 要输出的文字（引号包起来） |

> 麦叔的口诀：**print 打印，括号包，内容用引号**

---

## ❌ 常见错误

### 错误1：引号用了中文引号

```python
# ❌ 错误
print（"Hello World"）

# ✅ 正确
print("Hello World")
```

注意：要用英文的引号 `"` 而不是中文的 `""`

### 错误2：括号不匹配

```python
# ❌ 错误
print("Hello World"

# ✅ 正确
print("Hello World")
```

### 错误3：拼写错误

```python
# ❌ 错误
primt("Hello World")

# ✅ 正确
print("Hello World")
```

---

## 🏋️ 动手练习

### 练习1：打印你的名字

把 `print("Hello World")` 改成打印你自己的名字。

```python
print("你的名字")
```

### 练习2：打印一句你喜欢的话

比如：`print("我喜欢编程")`

### 练习3：连续打印多行

```python
print("第一行")
print("第二行")
print("第三行")
```

---

## 📝 今日要点

```
✅ Python 是一种编程语言，1991年诞生
✅ Python 可以做网站、数据分析、人工智能等
✅ 去 python.org 下载安装
✅ 安装时记得勾选 "Add Python to PATH"
✅ print("内容") 用来输出内容
✅ 引号和括号都要用英文的
```

---

## 🎖️ 本课徽章

完成本课练习获得：**🐣 第一行代码**

---

## 🎯 课后来挑战

1. 试试打印中文：`print("你好，世界")`
2. 试试打印 emoji：`print("😊")`
3. 想想还能打印什么？

---

## 📌 下节课预告

下节课我们会学到：
- 变量是什么
- 怎么给数据起名字
- 不同的数据类型

准备好了就告诉麦叔！👨‍🏫
