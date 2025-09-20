---
title: Text
date: 2025-08-25 00:30:29
tags:
	- 基础组件
categories:
	- Flutter
sticky: 20
cover: "https://s21.ax1x.com/2025/09/20/pV4wFqx.png"
---

文字显示和样式

<!-- more -->

# 组件 Text

基础使用

```dart
Text("Hello World"),
```



## Style 样式

文本样式通过属性 style 设置，值类型 TextStyle

### 常用属性

- 文字大小
- 文字家族
- 文字颜色
- 文字粗细
- 文字样式（倾斜）

TextStyle 类中属性

| 属性名     | 属性值类型 | 补充                                                         |
| ---------- | ---------- | ------------------------------------------------------------ |
| fontSize   | double     | 设置字体大小                                                 |
| fontFamily | String     | 设置字体家族                                                 |
| color      | Color      | 设置文字颜色                                                 |
| fontWeight | FontWeight | 设置字体粗细，值越大，文字越粗<br/>`FontWeight.w100`<br/>`FontWeight.w200`<br/>`FontWeight.w300`<br/>`FontWeight.w400`<br/>`FontWeight.w500`<br/>`FontWeight.w600`<br/>`FontWeight.w700`<br/>`FontWeight.w800`<br/>`FontWeight.w900`<br/>`FontWeight.normal` 等价于 `FontWeight.w400` <br/>`FontWeight.bold`等价于 `FontWeight.w700` <br/> |
| fontStyle  | FontStyle  | 设置字体样式<br/>`FontStyle.normal` 正常(默认值)<br/>`FontStyle.italic`倾斜 |



```dart
Text(
    "Hello World",
    style: TextStyle(
        fontSize: 30,
        fontFamily: "微软雅黑",
        color: Colors.red,
        fontWeight: FontWeight.w900,
        fontStyle： FontStyle.italic,
    ),
)
```

### 文字装饰线

TextStyle 类中属性

| 属性名              | 属性值类型          | 补充                                                         |
| ------------------- | ------------------- | ------------------------------------------------------------ |
| decoration          | TextDecoration      | 设置文字装饰线位置<br>`TextDecoration.lineThrough`  中划线<br/>` TextDecoration.underline `下划线<br/>`TextDecoration.overline` 上划线 |
| decorationColor     | Color               | 设置文字装饰线的颜色                                         |
| decorationStyle     | TextDecorationStyle | 设置文字装饰线的样式<br>`TextDecorationStyle.dotted` 点划线<br/>`TextDecorationStyle.dashed` 虚线<br/>`TextDecorationStyle.double`双实线<br/>`TextDecorationStyle.solid`实现<br/>`TextDecorationStyle.wavy` 波浪线 |
| decorationThickness | double              | 设置字体装饰线粗细                                           |



```dart
Text(
    "Hello World",
    style: TextStyle(
        fontSize: 30,
        decoration: TextDecoration.lineThrough,
        decorationColor: Colors.green,
        decorationStyle: TextDecorationStyle.dotted,
        decorationThickness: 3,
    ),
)
```

### 字母、单词间距

TextStyle 类中属性

| 属性名        | 属性值类型 | 补充               |
| ------------- | ---------- | ------------------ |
| letterSpacing | double     | 设置字母之间的间距 |
| wordSpacing   | double     | 设置单词之间的间距 |



```dart
Text("Hello World", style: TextStyle(letterSpacing: 5)),
Text("Hello World", style: TextStyle(wordSpacing: 30)),
Text(
    "This is 张三.",
    style: TextStyle(letterSpacing: 10, wordSpacing: 30),
),
```

> 使用 `letterSpacing` 设置汉字之间的间距，`wordSpacing` 属性对汉字无效

### 背景颜色、阴影

TextStyle 类中属性

| 属性名          | 属性值类型     | 补充             |
| --------------- | -------------- | ---------------- |
| backgroundColor | Color          | 设置文字背景颜色 |
| shadows         | `List<Shadow>` | 设置文字阴影     |



```dart
Text("Hello World", style: TextStyle(backgroundColor: Colors.red)),
```

`shadows` 设置文字阴影，文字可以设置多个方向的阴影， Shadow 属性

| 属性名     | 属性值类型                     | 补充                                                         |
| ---------- | ------------------------------ | ------------------------------------------------------------ |
| color      | Color                          | 设置文字背景颜色                                             |
| offset     | `Offset(double dx, double dy)` | 设置文字阴影方向<br/>`dx` 表示水平方向偏移，向右为正，向左为负<br/>`dy` 表示垂直方向偏移，向下为正，向上为负 |
| blurRadius | double                         | 设置文字阴影模糊值<br>值越大，阴影越模糊                     |

```dart
Text(
    "Hello World",
    style: TextStyle(
        fontSize: 30,
        shadows: [
            Shadow(
                color: Colors.red,
                offset: Offset(10, 10),
                blurRadius: 5,
            ),
            Shadow(
                color: Colors.green,
                offset: Offset(-10, -10),
                blurRadius: 5,
            ),
            Shadow(
                color: Colors.purple,
                offset: Offset(-10, 10),
                blurRadius: 5,
            ),
        ],
    ),
),
```



## 自定义字体

以 `霸道总裁` 字体为例， 字体下载地址 [https://zitiku.org/font/53](https://zitiku.org/font/53)

**字体存储位置**

字体存储位置可以自定义，比如：在项目根目录创建目录 `asset/fonts`, 将下载字体存放到 `asset/fonts` 目录

**字体配置**

编辑文件 `pubspec.yaml` 添加字体配置

```yaml
flutter:
	fonts:
        - family: "霸道总裁"
          fonts:
          	- asset: "asset/fonts/霸道总裁.ttf"
```

假如有多个字体需要添加， 配置

```yaml
flutter:
    fonts:
        - family: "字体1"
          fonts:
            - asset: "asset/fonts/字体1.ttf"
        - family: "字体2"
          fonts:
            - asset: "asset/fonts/字体2.ttf"
```



```dart
Text(
    "好日子, hello world",
    style: TextStyle(
        fontFamily: "霸道总裁",
        fontSize: 50,
        fontStyle: FontStyle.italic,
        fontWeight: FontWeight.w900,
    ),
),
```



## 疑问？

以下两个属性无效

文字对齐方式 `textAlign`

文字方向 `textDirection` 



