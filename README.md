# rot3dimage
采用css3技术，小巧轻便，可用于博客构建，网站，原生简单的3D轮播图插件。

#### 导读
1，引入./dist/css/rot3dimage.css和./dist/js/rot3dimage.js
```
<link rel="stylesheet" href="./dist/rot3dimage.css">
<script src="./dist/rot3dimage.js"></script>
```
2，添加配置信息
```js
    document.getElementById("test").slice3dPoster({
        hrefArr: ["http://www.baidu.com", "#2", "#3", "#4", "#5"], //分别代表对应的连接
        pageImgArr: ["./src/img/1.jpg", "./src/img/2.jpg", "./src/img/3.jpg", "./src/img/4.jpg", "./src/img/5.jpg"], //分别代表对应的图片
        cutIntoSlicesNumber: 5,//切割数（最好是宽度能够整除的一个数）
        switchTime: 0.1,//每个切片间延迟多长时间
        slicesTime: 2,//切片运动的时间
        lateralRotation: false,//是否横向旋转
        automatic: true,//是否自动切屏
        automaticTime: 2,//自动切屏时间
        changeButton: true
    });
```
#### 可以自定义左右按钮
先把`changeButton`配置选项设置为false
在调用`.setLeftEle()`和`.setRightEle()`方法添加元素到slice3dPoster实例中
像这样：
```js
slice3dPoster.setLeftEle(document.getElementById("test-left"));
slice3dPoster.setRightEle(document.getElementById("test-right"));
```

#### 案例
```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <title>test</title>
    <link rel="stylesheet" href="./dist/rot3dimage.css">
    <style>
        #test {
            height: 500px;
            width: 1000px;
        }
    </style>
</head>
<body>
<div id="test"></div>
<div id="test-left"><h1>1</h1></div>
<div id="test-right"><h1>2</h1></div>


<script src="./dist/rot3dimage.js"></script>
<script>
    document.getElementById("test").slice3dPoster({
        hrefArr: ["http://www.baidu.com", "#2", "#3", "#4", "#5"],
        pageImgArr: ["./src/img/1.jpg", "./src/img/2.jpg", "./src/img/3.jpg", "./src/img/4.jpg", "./src/img/5.jpg"],
        cutIntoSlicesNumber: 5,//切割数（最好是宽度能够整除的一个数）
        switchTime: 0.1,//每个切片间延迟多长时间
        slicesTime: 2,//切片运动的时间
        lateralRotation: false,//是否横向旋转
        automatic: true,//是否自动切屏
        automaticTime: 2,//自动切屏时间
        changeButton: false
    });
    //自定义左右按钮
    //点击1或2，可以翻页
    slice3dPoster.setLeftEle(document.getElementById("test-left"));
    slice3dPoster.setRightEle(document.getElementById("test-right"));
</script>
</body>
</html>
```

