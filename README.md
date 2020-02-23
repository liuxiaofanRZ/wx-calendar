# 微信小程序组件--日历组件

## 介绍

微信小程序没有好用的日历组件，特此封装简易的日历组件，方便项目开发。

## 安装

小程序支持使用 npm 安装第三方包，详见 [npm 支持](https://developers.weixin.qq.com/miniprogram/dev/devtools/npm.html?search-key=npm)

```bash
npm install wx-calendar --save
```

## 使用组件

在 json 文件中引入组件

```
{
  "usingComponents": {
    "calendar":"/miniprogram_npm/wx-calendar/calendar/index"
  }
}
```

接着就可以在 wxml 中直接使用组件

```html
<calendar />
```

## 文档

### 属性:

#### daysProps

```js
[
    d: 14,                           // 要设定的 日
    set: {                           // 该日配置
    	class: 'custom-date-style',  	// 该日自定义类名，默认 ''
    	disabled: true,              	// 不可选，默认 false
    },
    d: 1,
    set: {
    	class: 'custom-date-style',
    	disabled: true,
    },
]
```

#### props

```js
{
	disabledOtherMonth: true,       // 非本月日期不可选，默认 false
	showOtherMonth: true,			// 显示非本月日期，默认 false
	single: true					// 显示‘双数’，如‘01’而不是‘1’，默认 false
}
```

#### loading

```js
true | false						// 控制显示‘加载中’层
```

#### weeks

```js
['Sun','Mon','Tues','Wed','Thur','Fri','Sat']   // 自定义星期
```

### 事件：

#### onswitch

切换年（月）触发的事件，返回如下

```
// 返回切换后的年和月（可扩展）：
event.detail = {year: "2020", month: "03"}
```

#### onselect

选择日期后触发的事件，返回如下

```
{
    "week": 4,
    "y": "2020",
    "m": "02",
    "d": "06",
    "type": "on", // 该日期是否属于当月
    "total": "2020-02-06",
    "disabled": false,
    "visible": true,
    "selected": false,
    "class": "",
    "isToday": false
}
```



