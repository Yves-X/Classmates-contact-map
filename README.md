# 同学联络地图

一个 [ECharts](https://github.com/ecomfe/echarts) 的简单应用。

[Demo](https://dn-yvesx.qbox.me/demo/ClassmatesContactMap/demo.html)

# 使用说明

## 1. 引入关键文件

### ECharts库

文件名：

`echarts.min.js`

说明：

提供图表的核心功能。

此处提供的文件只包括联络地图所需组件，并经过压缩。

你还可以：

- 在 [ECharts 的官网](http://echarts.baidu.com/download.html)下载其他版本

- 在 [ECharts 的 Github 仓库](https://github.com/ecomfe/echarts)获取最新 Release

- [npm 安装 ECharts](http://echarts.baidu.com/tutorial.html#%E5%9C%A8%20webpack%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20ECharts)

- CDN 引入，例如： [BootCDN](http://www.bootcdn.cn/echarts/) 或 [CDNJS](https://cdnjs.com/libraries/echarts)，[NPMCDN](https://npmcdn.com/echarts@latest/dist/)

### 成员和位置数据

文件名：

`data.js`

说明：

提供联络地图所展示的数据。

此处提供的文件是一个示例，你可以参考修改。

### 地图

文件名：

`china.js`

说明：

提供联络地图所需的地图信息。

你还可以[下载其他地图](http://echarts.baidu.com/download-map.html)自行调用。

### 配置文件

文件名：

`option.js`

说明：

提供显示图表所需的配置信息，此处兼有主要地级市的位置信息。

你可以通过修改它实现[自定义](https://github.com/Yves-X/Classmates-Contact-Map#自定义)。

## 2. 提供一个具有确定尺寸的 DOM

例如：

```html
<div id="main" style="width: 1024px;height: 768px;"></div>
```

## 3. 初始化一个实例

例如：

```html
<script>var myChart = echarts.init(document.getElementById('main'));</script>
```

## 4. 应用配置文件显示图表

例如：

```html
<script>myChart.setOption(option);</script>
```

## 一个完整的示例

```html
<!DOCTYPE html>
<html>
<header>
    <title>Demo</title>
    <meta charset="utf-8">
    <script src="data.js"></script>
    <script src="echarts.min.js"></script>
    <script src="china.js"></script>
    <script src="option.js"></script>
</header>

<body>
    <!-- Supply a DOM with absolute size for the chart-->
    <div id="main" style="width: 1024px;height: 768px;"></div>
    <script>
    // Initialize an instance based on the DOM
    var myChart = echarts.init(document.getElementById('main'));
    // Apply
    myChart.setOption(option);
    </script>
</body>

</html>
```

## 自定义

ECharts 提供了非常丰富的配置项目，修改你的配置文件即可。

你可以参考[官方文档](http://echarts.baidu.com/option.html)。

## 注意

1. 要使图表能够正常显示，请确保以下顺序正确：
ECharts 库须在初始化之前引入。
数据文件须在配置文件之前引入。
配置文件须在应用之前引入。

2. 要使散点图能在地图上显示，需要提供地级市的位置信息。
此处只提供了主要城市的信息（在配置文件中），所以无法显示所有城市。
你可以自行拓展。
如果拓展信息的量大于目前规模，建议独立出来，或者考虑异步加载。