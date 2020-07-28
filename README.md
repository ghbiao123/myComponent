# myComponent
小程序-自定义模块

# 1. star

![1595921491148](C:\Users\王彪\AppData\Roaming\Typora\typora-user-images\1595921491148.png)

星级的展示，需要用到static中的图片

```html
<star num="3" size="30" comment="{{true}}" bind:star="myEvent"></star>
```



```js
properties:{
    // num， 黄色星星的数量
     num:{ 
      type:Number,
      value:0
    },
    // size, 星星的大小，单位rpx，默认大小30rpx
    size:{
      type:Number,
      value:30
    },
    // comment 是否可点击来进行选择星星数量，默认false
    comment:{
      type: Boolean,
      value: false
    }
}
methods:{
    // 将num值传递给父组件
    comment(e){
      if(!this.__data__.comment) return;
      let num = e.currentTarget.dataset.num;
      this.setData({ num });
      this.triggerEvent("star",num);
    }
  }
```

# 2.search

![1595923983112](C:\Users\王彪\AppData\Roaming\Typora\typora-user-images\1595923983112.png)

搜索框，可更换背景颜色

```html
<search-bar bind:mysearchbar="myEvent"></search-bar>
```

```js
properties:{
    // input's placeholder
    placeholder:{
      type: String,
      value:"搜索"
    },
    // cover's plaeholder
    coverholder:{
      type: String,
      value:"搜索"
    },
    // theme background-color
    theme:{
      type:String,
      value:'#f5f5f5'
    }
  },
```

