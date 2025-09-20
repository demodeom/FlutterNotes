---
title: Image
date: 2025-08-25 00:33:54
tags:
	- 基础组件
categories:
	- Flutte
cover: "https://s21.ax1x.com/2025/09/20/pV4wFqx.png"
---

图片

<!-- more -->

## 基础使用

### 网络图片

```bash
Image.network("https://s21.ax1x.com/2025/01/24/pEE9ToV.jpg")
```

### 本地图片

图片下载地址 [https://s21.ax1x.com/2025/01/06/pE9euv9.jpg](https://s21.ax1x.com/2025/01/06/pE9euv9.jpg)

1. 创建目录存储本地图片, 在项目根目录创建目录 `asset/images`, 将下载图片存放到 `asset/images` 目录
1. 编辑文件 `pubspec.yaml` 添加图片配置

```yaml
flutter:
    assets:
		- asset/images/pE9euv9.jpg
```

3. 重启项目（修改 `pubspec.yaml` 文件， 重启项目生效）

使用本地图片

```dart
Image.asset("asset/images/pE9euv9.jpg")
```



### 图片大小

`width` 属性设置宽度，`height` 属性设置高度；

可以只设置宽度或者高度， 也可以同时设置宽度和高度

```dart
Image.network(
    "https://s21.ax1x.com/2025/01/24/pEE9ToV.jpg",
    width: 200,
    height: 100,
),
```

```dart
Image.asset(
    "asset/images/pE9euv9.jpg", 
    width: 200,
    height: 100,
)
```



## 图片适配

当图片宽高和容器宽高不一致，可以使用 `fit` 属性设置图片显示方式

图片属性

| 属性名 | 属性值类型 | 补充                                                         |
| ------ | ---------- | ------------------------------------------------------------ |
| fit    | BoxFit     | 设置图片显示方式<br>`BoxFit.fitWidth` 适配宽度<br/>`BoxFit.fitHeight` 适配宽度<br/>`BoxFit.contain` 包含<br/>`BoxFit.fill` 填充<br/>`BoxFit.cover` 裁剪 |

常用属性 `BoxFit.cover` `BoxFit.contain`

```dart
Container(
    width: 300,
    height: 800,
    decoration: BoxDecoration(
        color: Colors.green,
        border: Border.all(color: Colors.red, width: 2),
    ),
    // 800 1063
    child: Image.network(
        "https://s21.ax1x.com/2025/01/24/pEE9ToV.jpg",
        fit: BoxFit.contain,
    ),
),
```













