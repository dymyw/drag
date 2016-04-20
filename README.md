# drag
jquery.drag.js - `jQuery` plugin

------

#### 使用说明
##### 引入必要的文件，当然还需要 `jQuery` 库
```javascript
<script type="text/javascript" src="jquery.drag.js"></script>
```

##### 参数列表
|      参数名     |       类型       |                     默认值                    |     说明     |
| -------------- | ---------------- | -------------------------------------------- | ------------ |
| handler        |     selector     |     null                                     | 鼠标拖动块元素的作用域，默认整个块元素 |
| areaLimit      |     boolean      |     false                                    | 是否只在父元素内部拖动 |
| areaLimitBox   |     object       |     {available: false, x: null, y: null}     | 是否给其定一个拖动限制范围，x 左右限制，单位 px、y 上下限制 |
| onMove         |     float        |     $.noop                                   | 拖动时执行的函数 |
| onDrop         |     float        |     $.noop                                   | 鼠标松开时执行的函数 |

##### 举例说明
```html
<div id="drag-test">
    <div id="title">Title - hander</div>
    <div id="content">
        content content content content content content content content content content content content content content content content content content content content content content content content content content content<br /><br />
        mouse position: <span></span>
    </div>
</div>
```

```javascript
$('#drag-test').drag({
    handler: $('#title'),
    areaLimit: true,
    areaLimitBox: {
        available: true,
        x: 20,
        y: 50
    },
    onMove: function(e) {
        console.log('move');
        console.log(e);
    },
//    onDrop: function() {
//        console.log('drop');
//    }
});
```
