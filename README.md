# CSS的知识盲点以及flex布局总结

## &符号代表什么意思？
这是sass的语法，代表上一级选择器。例“
```scss
.el-row{
    margin-bottom: 20px;
    &:last-child{
      margin-bottom: 0;
}//实际译成css就是.el-row:last-child{}
}
```

## 什么是伪元素？

伪元素是一个附加至选择器末的关键词，允许你对被选择元素的特定部分修改样式。下例中的`::first-line`伪元素可改变段落首行文字的样式。

```css
p::first-line{
    color: blue;
    text-transform: uppercase;
}
```

### 常见的伪元素有哪些？
`::after` 用来创建一个伪元素，作为已选中元素的最后一个元素。通常会配合content属性来为该元素添加修饰内容。

`::bofore` 用来创建一个伪元素，作为已选中元素的第一个元素。通常会配合content属性来为该元素添加修饰内容。

`::first-letter` 会选中某 block-level element（块级元素）第一行的第一个字母，并且文字所处的行之前没有其他内容（如图片和内联的表格）。

`::first-line` 在某 block-level element （块级元素）的第一行应用样式。第一行的长度取决于很多因素，包括元素宽度，文档宽度和文本的文字大小。

`::selection` 应用于文档中被用户高亮的部分（比如使用鼠标或其他选择设备选中的部分）。

## flex布局的知识点

1. `justify-content` 可以水平对齐元素，并且接受一下参数：

* `flex-start` : 元素和容器的左端对齐。
* `flex-end` : 元素与容器的右端对齐。
* `center` : 元素在容器里居中。
* `space-between`: 元素之间保持相等的距离。
* `space-around`: 元素周围保持相等的距离。

2. `align-items` 用于纵向对齐元素，并且可以选择以下几个值：
* `flex-start`: 元素与容器顶部对齐。
* `flex-end`: 元素与容器底部对齐。
* `center`: 元素纵向居中。
* `baseline` : 元素在容器的基线位置显示。
* `stertch` : 元素被拉伸以填满整个容器。

3. `flex-direction` 定义了元素在容器里摆放的方向，并且接受这些值：
* `row`: 元素摆放的方向和文字方向一致。
* `row-reverse`: 元素摆放的方向和文字方向相反。
* `column` ： 元素从上放到下。
* `column-reverse` :元素从下放到上。

4. `order` 通过设置单个元素的order来改变其排列顺序。元素的属性默认值为0。

5. `align-self`  接受和`align-items`一样的值，控制单个元素的纵向对齐。

6. `flex-wrap` 用于控制元素是否换行。它接受以下的值：
* `nowrap`: 所有的元素都在一行。
* `wrap`： 元素自动换成多行。
* `wrap-reverse`:元素自动换成逆序的多行。

7. `flex-flow` 由于flex-direction和flex-wrap两个属性经常会一起使用，所有有了缩写属性`flex-flow`。这个缩写属性接受两个属性的值，中间用空格隔开。

8. `align-content` 用于决定行与行之间的间隔。这个属性接受以下的值：
* `flex-start`: 多行集中于顶部。
* `flex-end`： 多行集中于尾部。
* `center`： 多行居中。
* `space-between`： 行与行之间保持相等距离。
* `space-around`： 每行的周围保持相等距离。
* `stretch`: 每一行都被拉伸以填满容器。