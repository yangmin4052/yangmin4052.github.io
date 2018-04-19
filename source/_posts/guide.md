## 解决 vue 使用 echarts 时宽高等比例问题

### 具体代码参见 ChartTest.vue

---

* template 中 echart 绘制

```
<template>
    <div id="myChart" :style="{width: width, height:height}"></div>
</template>
```

---

* data 中填写如下三项

```
    data() {
        echartWidth: '',// resize后存放echart的宽
        echartHeight: '',// resize后存放echart的高
        scale:2,// echart的宽高比
        //其他代码
    }
```

* methods 中代码如下

```
methods:{
    // echart渲染
    drawLine() {
        // 基于准备好的dom，初始化echarts实例
        let myChart = echarts.init(document.getElementById('myChart'))
        // 绘制图表
        myChart.setOption(this.option);
        // 宽度自适应 resize后canvas重绘
        window.addEventListener("resize", function() {
            setTimeout(() => {
            myChart.resize();
            }, 500)
        });
    },
    // 获取resize后的echart的宽高
    chartResize() {
        window.addEventListener("resize", ()=> {
            this.echartWidth = document.body.clientWidth + 'px';
            this.echartHeight = parseFloat(this.echartWidth)/this.scale+'px';
        });
    }
}
```

* mounted 中代码如下

```
mounted() {
    this.drawLine();// echart渲染
    this.chartResize();// 获取resize后的echart的宽高
}
```

computed 中代码如下

```
computed: {
    // 获取初次绘echart时的宽度
    defaultWidth() {
        return document.body.clientWidth + 'px';
    },
    // 获取初次绘echart时的高度
    defaultHeight() {
        return parseFloat(this.defaultWidth)/this.scale+'px';
    },
    // 获取echart的现在需要绘制的宽度
    width() {
        return this.echartWidth?this.echartWidth:this.defaultWidth;
    },
    // 获取echart的现在需要绘制的高度
    height() {
        return this.echartHeight?this.echartHeight:this.defaultHeight;
    }
} 
```
