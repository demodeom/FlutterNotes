---
title: Alert
date: 2025-08-25 00:33:54
tags:
	- 基础组件
categories:
	- Flutter
cover: "https://s21.ax1x.com/2025/09/20/pV4wFqx.png"
---



材料设计警报对话框。
警报对话框（也称为基本对话框）将需要确认的情况通知用户。警报对话框具有可选标题和可选的操作列表。标题显示在内容上方，操作显示在内容下方。

<!-- more -->



## AlertDialog



| 属性名  | 属性值类型     | 补充                     |
| ------- | -------------- | ------------------------ |
| title   | Widget         | 标题                     |
| content | Widget         | 弹窗内容                 |
| actions | `List<Widget>` | 行为（一个或者多个按钮） |

```dart
AlertDialog(
    title: Text("弹窗"),
    content: Text("登录成功"),
    actions: [
        TextButton(
            onPressed: () => {Navigator.pop(context)},
            child: Text("取消"),
        ),
        TextButton(
            onPressed: () => {Navigator.pop(context)},
            child: Text("确定"),
        ),
    ],
),
```



## showDialog

在应用程序的当前内容上方显示一个对话框，并带有显示和关闭对话框动画，模态屏障颜色和模态屏障行为（对话框在障碍物上的点击是可以忽略的）。

| 属性名             | 属性值类型   | 补充                                                         |
| ------------------ | ------------ | ------------------------------------------------------------ |
| context            | BuildContext | 标题                                                         |
| barrierDismissible | bool         | 是否允许点击背景关闭警告框<br />`false `不允许<br />`true` 允许 |
| builder            | Function     | 函数（返回AlertDialog）                                      |

警告框触发方式有很多， 最常见的按钮的点击事件：

```dart
OutlinedButton(
    onPressed: () => {
      showDialog(
        context: context,
        barrierDismissible: false,
        builder: (BuildContext context) => AlertDialog(
          title: Text("弹窗"),
          content: Text("登录成功"),
          actions: [
            TextButton(
              onPressed: () => {Navigator.pop(context)},
              child: Text("取消"),
            ),
            TextButton(
              onPressed: () => {Navigator.pop(context)},
              child: Text("确定"),
            ),
          ],
        ),
      ),
    },
    child: Text("登录"),
  ),
```

