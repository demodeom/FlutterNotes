---
title: Icon
date: 2025-08-25 00:30:29
tags:
	- 基础组件
categories:
	- Flutter
cover: "https://s21.ax1x.com/2025/09/20/pV4wFqx.png"
---

Icon

<!-- more -->



Icon 文档地址 [https://github.com/flutter/flutter/blob/main/docs/libraries/material/Updating-Material-Design-Fonts-%26-Icons.md](https://github.com/flutter/flutter/blob/main/docs/libraries/material/Updating-Material-Design-Fonts-%26-Icons.md)



## 基础使用

Icon 属性

| 属性名        | 属性值类型     | 补充               |
| ------------- | -------------- | ------------------ |
| icon          | IconData       | Flutter 内置很icon |
| size          | Dobule         | 大小               |
| color         | Color          | 颜色               |
| shadows       | `List<Shadow>` |                    |
| semanticLabel | String         | 为图标翻译语义标签 |



```dart
Icon(Icons.flag, size: 50,color: Colors.red, semanticLabel: "flag")
```

