# Class 与 Style 绑定
在 v-bind 用于 class 和 style 时， Vue.js 专门增强了它。表达式的结果类型除了字符串之外，还可以是对象或数组。
### 绑定HTML Class
##### 对象语法
**给v-bind:class传入一个对象**，以动态的切换class。
v-bind:class可以与class属性共存；
`<div v-bind:class="{ active: isActive }"></div>`: 实际渲染结果取决于isActive是true还是false；
> 注：这里class如果是有连字符的，例如alert-success，需要加引号；

**也可以直接绑定数据里的一个对象**，该对象也可以绑定计算属性；
`<div v-bind:class="classObj"></div>`
````javascript
data: {
    classObj: {
        qwe: true,
        asd: false
    }
}
````

##### 数组语法
我们可以把一个数组传给 v-bind:class ，以应用一个 class 列表：
`<div v-bind:class="[activeClass, errorClass]">asd</div>`
````javascript
data: {
    activeClass: active,
    errorClass: error
}
````
渲染结果为`<div class="active error">asd</div>`
数组语法中也可以使用对象语法
##### 用在组件上
