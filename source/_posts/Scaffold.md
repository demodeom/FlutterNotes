---
title: Scaffold
date: 2025-08-25 00:30:29
tags:
	- 基础组件
categories:
	- Flutter
cover: "https://s21.ax1x.com/2025/09/20/pV4wFqx.png"
---

文字显示和样式

<!-- more -->



## MaterialApp



## Scaffold

> Implements the basic Material Design visual layout structure.
>
> This class provides APIs for showing drawers and bottom sheets.
>
> 实现基本的 Material Design 视觉布局结构。
>
> 此类提供用于显示抽屉和底部操作条的 API。



| 属性名          | 属性值类型 | 补充                 |
| --------------- | ---------- | -------------------- |
| appBar          | AppBar     | 子元素               |
| body            | Widget     |                      |
| backgroundColor | Color      | 设置（body）背景颜色 |



| 属性名                       | 属性值类型                   | 补充         |
| ---------------------------- | ---------------------------- | ------------ |
| floatingActionButton         | Widget                       | 浮动按钮     |
| floatingActionButtonLocation | FloatingActionButtonLocation | 浮动按钮位置 |





| 属性名                       | 属性值类型                   | 补充         |
| ---------------------------- | ---------------------------- | ------------ |
| bottomNavigationBar          | BottomNavigationBar          | 底部导航     |
| floatingActionButtonLocation | FloatingActionButtonLocation | 浮动按钮位置 |



| 属性名 | 属性值类型 | 补充 |
| ------ | ---------- | ---- |
| drawer | Widget     | 抽屉 |
|        |            |      |





### AppBar



### FloatingActionButton

| 属性名    | 属性值类型 | 补充     |
| --------- | ---------- | -------- |
| onPressed | Function   | 点击事件 |
| child     | Widget     | 子元素   |





```dart
Scaffold(
	// ...
    floatingActionButton: FloatingActionButton(
      onPressed: ()=>{},
      child: const Icon(Icons.add),
    ),
);
```



| 属性名          | 属性值类型 | 补充     |
| --------------- | ---------- | -------- |
| tooltip         | Function   | 点击事件 |
| backgroundColor | Color      |          |
| foregroundColor | Color      |          |



### FloatingActionButtonLocation

[https://api.flutter.dev/flutter/material/FloatingActionButtonLocation-class.html](https://api.flutter.dev/flutter/material/FloatingActionButtonLocation-class.html)





### BottomNavigationBar



| 属性名          | 属性值类型                      | 补充                               |
| --------------- | ------------------------------- | ---------------------------------- |
| items           | `List<BottomNavigationBarItem>` | 子元素                             |
| onTap           | Function                        | 点击事件                           |
| currentIndex    | Widget                          | 当前选中的 BottomNavigationBarItem |
| backgroundColor | Color                           | 背景颜色                           |
| iconSize        | double                          | 图标大小                           |





| 属性名             | 属性值类型 | 补充                              |
| ------------------ | ---------- | --------------------------------- |
| selectedItemColor  | Color      | 选中 BottomNavigationBar 颜色     |
| selectedFontSize   | double     | 选中 BottomNavigationBar 字体大小 |
| selectedLabelStyle | TextStyle  | 选中 BottomNavigationBar 标签样式 |
| showSelectedLabels | bool       | 显示选中 BottomNavigationBar 标签 |





| 属性名               | 属性值类型 | 补充                                |
| -------------------- | ---------- | ----------------------------------- |
| unselectedItemColor  | Color      | 未选中 BottomNavigationBar 颜色     |
| unselectedFontSize   | double     | 未选中 BottomNavigationBar 字体大小 |
| unselectedLabelStyle | TextStyle  | 未选中 BottomNavigationBar 标签样式 |
| showUnselectedLabels | bool       | 显示未选中 BottomNavigationBar 标签 |



> [selectedItemColor] 和 [fixedColor] 只能指定一个。首选前者，[fixedColor] 仅用于向后兼容。



### BottomNavigationBarItem



| 属性名          | 属性值类型 | 补充             |
| --------------- | ---------- | ---------------- |
| icon            | Widget     | 子元素           |
| label           | String     | 文本             |
| activeIcon      | Widget     | 选中时显示的图标 |
| backgroundColor | Color      | 背景颜色         |
| tooltip         | String     | 提示文本         |





### Drawer



| 属性名          | 属性值类型 | 补充           |
| --------------- | ---------- | -------------- |
| child           | Widget     | 子元素(Drawer) |
| backgroundColor | Color      | 背景颜色       |
| shadowColor     | Color      | 阴影颜色       |
| width           | double     | 宽度           |

`Drawer` 抽屉组件默认并不能直接打开， 需要配合事件来显示、隐藏抽屉， 通常配合标题栏的前置图标的点击事件来实现

打开抽屉

```dart
Scaffold.of(context).openDrawer();
```

关闭抽屉

```dart
Scaffold.of(context).closeDrawer();
```



```dart
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Example Text"),
        leading: Builder(
          builder: (context) {
            return IconButton(
              icon: const Icon(Icons.menu),
              onPressed: () {
                Scaffold.of(context).openDrawer();
              },
            );
          },
        ),
      ),
      backgroundColor: Colors.blueGrey,
      body: Column(children: [Text("data")]),
      bottomNavigationBar: BottomNavigationBar(
        items: [
          BottomNavigationBarItem(icon: Icon(Icons.home), label: "Home"),
          BottomNavigationBarItem(icon: Icon(Icons.history), label: "History"),
        ],
      ),
      drawer: Drawer(
        child: ListView(
          children: [
            DrawerHeader(
              padding: EdgeInsets.zero,
              decoration: BoxDecoration(color: Colors.blue),
              child: Text("Drawer Header"),
            ),
            ListTile(title: Text("Item 1")),
            ListTile(title: Text("Item 2")),
            ListTile(title: Text("Item 3")),
            ListTile(title: Text("Item 4")),
          ],
        ),
      ),
    );
  }
```



## SafeArea

> A widget that insets its child with sufficient padding to avoid intrusions by the operating system.
>
> 一个小部件，用足够的填充来插入它的子部件，以避免操作系统的入侵。

| 属性名 | 属性值类型 | 补充   |
| ------ | ---------- | ------ |
| child  | Widget     | 子元素 |





