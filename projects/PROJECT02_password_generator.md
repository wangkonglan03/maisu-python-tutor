# 🔐 项目2：密码生成器

## 📖 项目目标

- 练习字符串操作、random模块
- 练习列表、循环
- 完成一个实用的小工具

---

## 🎯 项目需求

生成随机密码：
- 可选长度（8-32位）
- 可选包含：大小写字母、数字、特殊符号
- 一键生成

---

## 📝 代码

```python
import random
import string

def 生成长度(密码长度, 使用大写, 使用小写, 使用数字, 使用符号):
    """根据设置生成密码"""
    
    # 收集所有可用的字符
    可用字符 = ""
    
    if 使用大写:
        可用字符 += string.ascii_uppercase  # A-Z
    if 使用小写:
        可用字符 += string.ascii_lowercase  # a-z
    if 使用数字:
        可用字符 += string.digits          # 0-9
    if 使用符号:
        可用字符 += "!@#$%^&*()_+-=[]{}|;:,.<>?"
    
    # 如果什么都没选，用小写字母
    if not 可用字符:
        可用字符 = string.ascii_lowercase
    
    # 随机选择字符
    密码 = ""
    for _ in range(密码长度):
        密码 += random.choice(可用字符)
    
    return 密码

def main():
    print("=" * 40)
    print("🔐 麦叔密码生成器")
    print("=" * 40)
    
    # 获取长度
    while True:
        长度 = input("密码长度（8-32，输入数字）：")
        if 长度.isdigit():
            长度 = int(长度)
            if 8 <= 长度 <= 32:
                break
        print("⚠️ 请输入8-32之间的数字！")
    
    # 获取选项
    print("\n选择要包含的字符类型：")
    使用大写 = input("大写字母(A-Z)? (y/n)：").lower() == 'y'
    使用小写 = input("小写字母(a-z)? (y/n，默认y)：").lower() in ['y', '']
    使用数字 = input("数字(0-9)? (y/n，默认y)：").lower() in ['y', '']
    使用符号 = input("特殊符号(!@#$)? (y/n，默认y)：").lower() in ['y', '']
    
    # 生成密码
    密码 = 生成长度(长度, 使用大写, 使用小写, 使用数字, 使用符号)
    
    print("\n" + "=" * 40)
    print(f"🔑 生成的密码：{密码}")
    print("=" * 40)
    
    # 复制提示
    print("\n💡 提示：在密码上右键可以复制")

if __name__ == "__main__":
    main()
```

---

## 🔍 代码解析

### 1. import string
string模块包含很多有用的字符常量：
```python
string.ascii_uppercase  # "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
string.ascii_lowercase  # "abcdefghijklmnopqrstuvwxyz"
string.digits           # "0123456789"
```

### 2. random.choice()
从序列中随机选择一个元素：
```python
random.choice("ABC")  # 随机返回 "A" 或 "B" 或 "C"
```

---

## 🏆 扩展挑战

### 挑战1：密码强度检测
生成密码后，检测并显示强度（弱/中/强）

### 挑战2：批量生成
一次生成多个密码

### 挑战3：记忆功能
把生成的密码保存到文件

### 挑战4：密码要求保障
确保密码至少包含一种选中的字符类型

---

## 🎖️ 完成后获得

🔐 **密码专家** 徽章

---

_有问题随时问麦叔！_
