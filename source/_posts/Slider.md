---
title: Slider
date: 2025-09-02 14:57:17
tags:
  - 基础组件
categories:
  - Flutter
cover: "https://s21.ax1x.com/2025/09/20/pV4dT2j.png"
description: "Slider"
---

Slider

<!-- more -->

## Slider

```
Slider(
            value: age,
            min: 0,
            max: 100,
            divisions: 4,
            label: "$age",
            onChanged: (value) {
              setState(() {
                age = value;
              });
            },
          ),
```



## RangeSlider

```
RangeSlider(
            values: selectedRange,
            min: 0,
            max: 100,
            divisions: 4,
            labels: RangeLabels("${selectedRange.start}", "${selectedRange.end}"),
            onChanged: (value) {
              setState(() {
                selectedRange = value;
              });
            },
          ),
```



## CupertinoSlider

An iOS-style slider.







