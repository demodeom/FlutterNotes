---
title: ListTitle
date: 2025-08-25 00:30:29
tags:
	- 基础组件
categories:
	- Flutter
cover: "https://s21.ax1x.com/2025/09/20/pV4wFqx.png"
---

文字显示和样式

<!-- more -->



## 基础使用

`ListTitle` 属性

| 属性名   | 属性值类型 | 补充                 |
| -------- | ---------- | -------------------- |
| title    | Widget     | 标题                 |
| subtitle | Widget     | 副标题               |
| leading  | Widget     | 标题前显示的小部件。 |
| trailing | Widget     | 标题后显示的小部件。 |

`ListTitle` 属性

| 属性名                      | 属性值类型 | 补充                                           |
| --------------------------- | ---------- | ---------------------------------------------- |
| titleTextStyle              | TextStyle  | 标题样式                                       |
| subtitleTextStyle           | TextStyle  | 副标题样式                                     |
| leadingAndTrailingTextStyle | TextStyle  | 标题前显示的小部件和标题后显示的小部件文本样式 |

`ListTitle` 属性

| 属性名             | 属性值类型 | 补充                       |
| ------------------ | ---------- | -------------------------- |
| minLeadingWidth    | double     | 标题前显示的小部件最小宽度 |
| minTileHeight      | double     | 标题最小高度               |
| minVerticalPadding | double     | 标题后显示的小部件最小宽度 |

```dart
ListTile(
    title: Text(
        "AMD 正测试新一代“Medusa Point”移动处理器：采用 FP10 接口，默认 TDP 45W",
        maxLines: 1,
    ),
    subtitle: Text(
        "AMD下一代\"Medusa Point\"处理器细节曝光：采用FP10插槽，TDP提升至45W，基于Zen 6架构，面向高端及主流笔记本市场。预计将采用台积电3nm工艺，最多22核，iGPU性能也有望提升。",
        maxLines: 2,
    ),
    leading: Image.network(
    	"https://s21.ax1x.com/2025/01/24/pEE9ToV.jpg",
    ),
    trailing: Icon(Icons.arrow_forward_ios),
    titleTextStyle: TextStyle(color: Colors.black),
    subtitleTextStyle: TextStyle(color: Colors.black54),
    minLeadingWidth: 50,
    minTileHeight: 30,
    selected: true,
),
```

