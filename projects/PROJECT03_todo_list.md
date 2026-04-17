# 📋 项目3：待办事项清单（Todo List）

## 📖 项目目标

- 综合练习列表、字典、循环、条件判断
- 理解文件读写基础
- 完成一个实用的命令行工具

---

## 🎯 项目需求

一个命令行待办事项管理工具：
- 添加待办事项
- 查看待办列表
- 标记完成
- 删除待办
- 保存到文件

---

## 📝 代码

```python
import json
import os

文件路径 = "todos.json"

def 加载待办():
    """从文件加载待办事项"""
    if os.path.exists(文件路径):
        with open(文件路径, "r", encoding="utf-8") as f:
            return json.load(f)
    return []

def 保存待办(待办列表):
    """保存待办事项到文件"""
    with open(文件路径, "w", encoding="utf-8") as f:
        json.dump(待办列表, f, ensure_ascii=False, indent=2)

def 显示菜单():
    print("\n" + "=" * 40)
    print("📋 麦叔待办事项")
    print("=" * 40)
    print("1. 查看待办")
    print("2. 添加待办")
    print("3. 完成待办")
    print("4. 删除待办")
    print("5. 退出")
    print("=" * 40)

def 显示待办(待办列表):
    if not 待办列表:
        print("\n📭 目前没有待办事项！")
        return
    
    print("\n📝 待办事项：")
    for i, 待办 in enumerate(待办列表, 1):
        状态 = "✅" if 待办["完成"] else "⬜"
        优先级 = 待办.get("优先级", "中")
        print(f"{i}. {状态} [{优先级}] {待办['内容']}")
    
    # 统计
    总数 = len(待办列表)
    已完成 = sum(1 for t in 待办列表 if t["完成"])
    print(f"\n进度：{已完成}/{总数} 完成")

def 添加待办(待办列表):
    内容 = input("输入待办内容：")
    if not 内容.strip():
        print("⚠️ 内容不能为空！")
        return 待办列表
    
    print("优先级：1. 高  2. 中  3. 低")
    优先级选择 = input("选择（默认中）：") or "2"
    
    优先级_map = {"1": "高", "2": "中", "3": "低"}
    优先级 = 优先级_map.get(优先级选择, "中")
    
    待办 = {
        "内容": 内容,
        "完成": False,
        "优先级": 优先级
    }
    
    待办列表.append(待办)
    print("✅ 添加成功！")
    return 待办列表

def 完成待办(待办列表):
    if not 待办列表:
        print("📭 没有待办事项！")
        return 待办列表
    
    显示待办(待办列表)
    编号 = input("\n输入要完成的编号：")
    
    if 编号.isdigit():
        索引 = int(编号) - 1
        if 0 <= 索引 < len(待办列表):
            待办列表[索引]["完成"] = True
            print(f"✅ 已完成：{待办列表[索引]['内容']}")
        else:
            print("⚠️ 编号不存在！")
    
    return 待办列表

def 删除待办(待办列表):
    if not 待办列表:
        print("📭 没有待办事项！")
        return 待办列表
    
    显示待办(待办列表)
    编号 = input("\n输入要删除的编号：")
    
    if 编号.isdigit():
        索引 = int(编号) - 1
        if 0 <= 索引 < len(待办列表):
            删除的 = 待办列表.pop(索引)
            print(f"🗑️ 已删除：{删除的['内容']}")
        else:
            print("⚠️ 编号不存在！")
    
    return 待办列表

def main():
    待办列表 = 加载待办()
    
    while True:
        显示菜单()
        choice = input("选择：")
        
        if choice == "1":
            显示待办(待办列表)
        elif choice == "2":
            待办列表 = 添加待办(待办列表)
            保存待办(待办列表)
        elif choice == "3":
            待办列表 = 完成待办(待办列表)
            保存待办(待办列表)
        elif choice == "4":
            待办列表 = 删除待办(待办列表)
            保存待办(待办列表)
        elif choice == "5":
            保存待办(待办列表)
            print("\n👋 再见！数据已保存。")
            break
        else:
            print("⚠️ 无效选择！")

if __name__ == "__main__":
    main()
```

---

## 🔍 代码解析

### 1. JSON 文件存储
```python
import json
json.dump(待办列表, f)   # 保存到文件
json.load(f)              # 从文件读取
```

### 2. 文件是否存在
```python
import os
if os.path.exists(文件路径):
    # 文件存在
```

---

## 🏆 扩展挑战

### 挑战1：支持截止日期
给待办添加截止日期

### 挑战2：分类标签
给待办添加分类（工作/生活/学习）

### 挑战3：排序功能
按优先级/完成状态/创建时间排序

### 挑战4：搜索功能
按关键词搜索待办

---

## 🎖️ 完成后获得

📝 **清单达人** 徽章

---

_有问题随时问麦叔！_
