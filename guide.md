# 前端开发规范指南

规范的目的是为了编写高质量的代码，让团队成员每天的心情都是愉悦的，大家在一起是快乐的。

## 一、编程规约

### (一)、命名规范

#### 1.1.1 命名分类

- `camelCase`（驼峰式，也叫小驼峰命名，`e.g. userInfo`）

- `PascalCase`（帕斯卡命名式，也叫大驼峰命名，`e.g. UserInfo`）

- `kebab-case`（短横线连接式，`e.g. user-info`）

- `snake_case`（下划线连接式，`e.g. user_info`）

#### 1.1.2 项目命名

全部采用小写方式， 以中划线分隔。

正例：`mall-management-system`

反例：`mall_management-system / mallManagementSystem`

#### 1.1.3 目录命名

全部采用小写方式， 以中划线分隔，有复数结构时，要采用复数命名法， 缩写不用复数

正例： `scripts / styles / components / images / utils / demo-styles / demo-scripts / doc`

反例： `script / style / demo_scripts / demoStyles / imgs / docs`

【特殊】VUE 的项目中的 components 中的组件目录需保持一致，且使用 PascalCase 命名（暂定，因为文件夹内部组件名要求 PascalCase 命名规范，且单词大写开头对于代码编辑器的自动补全最为友好，因为这使得我们在 JS(X) 和模板中引用组件的方式尽可能的一致）

正例： `HeadSearch / PageLoading`

反例： `head-search / page-loading / authorized / notice-icon`

#### 1.1.4 JS、CSS、SCSS、HTML、PNG 文件命名

全部采用小写方式， 以中划线分隔

正例： `render-dom.js / signup.css / index.html / company-logo.png`

反例： `renderDom.js / UserManagement.html`

#### 1.1.5 命名严谨性

代码中的命名严禁使用拼音与英文混合的方式，更不允许直接使用中文的方式。 说明：正确的英文拼写和语法可以让阅读者易于理解，避免歧义。注意，即使纯拼音命名方式也要避免采用

正例：`henan / luoyang / rmb 等国际通用的名称，可视同英文。`

反例：`DaZhePromotion [打折促销] / getPingfenByName() [评分] / int 某变量 = 3`

**杜绝完全不规范的缩写（如缩写多个单词、缩写冷门单词），避免望文不知义：**

正例：AbstractClass“缩写”命名成 AbsClass；Function“缩写成”Func, 这些命名缩写一看便明白意思
反例：condition“缩写”命名成 condi；businessLicenseCardId"缩写成"busLicCardId， 此类随意缩写严重降低了代码的可阅读性。

### (二) HTML 规范 （Vue Template 同样适用）

#### 1.2.1 HTML 类型

推荐使用 HTML5 的文档类型申明：
（建议使用 text/html 格式的 HTML。避免使用 XHTML。XHTML 以及它的属性，比如 application/xhtml+xml 在浏览器中的应用支持与优化空间都十分有限）。

- 规定字符编码

- IE 兼容模式

- doctype 大写

  正例：

  ```html
  <!DOCTYPE html>
  <html lang="en">
    <head>
      <meta charset="UTF-8" />
      <meta http-equiv="X-UA-Compatible" content="IE=edge" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <title>Document</title>
    </head>
    <body>
      <!--  -->
    </body>
  </html>
  ```

#### 1.2.2 缩进

缩进使用 2 个空格（一个 tab，1 个 tab=2 个空格）

嵌套的节点应该缩进。

#### 1.2.3 分块注释

在每一个块状元素，列表元素和表格元素后，加上一对 HTML 注释。注释格式

正例：

```html
<body>
  <!-- header 头部 start -->
  <header>
    <div class="container">
      <a href="#">
        <!-- 图片会把a标签给撑开，所以不用设置a标签的大小 -->
        <img src="images/header.jpg" />
      </a>
    </div>
  </header>
  <!-- header 头部 end -->
</body>
```

#### 1.2.4 语义化标签

HTML5 中新增很多语义化标签，所以优先使用语义化标签，避免一个页面都是 div 、span 或者 p 标签

正例

```html
<header></header>
<footer></footer>
```

反例

```html
<div>
  <p></p>
</div>
```

#### 1.2.5 引号

使用双引号(“ “) 而不是单引号(‘ ‘) 。

### (三) CSS 规范

#### 1.3.1 命名

- 类名使用小写字母，以中划线或下划线分隔
- id 采用驼峰式命名
- scss 中的变量、函数、混合、placeholder 采用驼峰式命名

ID 和 class 的名称总是使用可以反应元素目的和用途的名称，或其他通用的名称，代替表象和晦涩难懂的名称

不推荐：

```css
.fw-800 {
  font-weight: 800;
}

.red {
  color: red;
}
```

推荐:

```css
.heavy {
  font-weight: 800;
}

.important {
  color: red;
}
```

#### 1.3.2 选择器

1. css 选择器中避免使用标签名
   从结构、表现、行为分离的原则来看，应该尽量避免 css 中出现 HTML 标签，并且在 css 选择器中出现标签名会存在潜在的问题。

2. 很多前端开发人员写选择器链的时候不使用 直接子选择器（注：直接子选择器和后代选择器的区别）。有时，这可能会导致疼痛的设计问题并且有时候可能会很耗性能。然而，在任何情况下，这是一个非常不好的做法。如果你不写很通用的，需要匹配到 DOM 末端的选择器， 你应该总是考虑直接子选择器。

不推荐:

```css
.content .title {
  font-size: 2rem;
}
```

推荐:

```css
.content > .title {
  font-size: 2rem;
}
```

#### 1.3.3 尽量使用缩写属性

不推荐：

```css
border-top-style: none;
font-family: palatino, georgia, serif;
font-size: 100%;
line-height: 1.6;
padding-bottom: 2em;
padding-left: 1em;
padding-right: 1em;
padding-top: 0;
```

推荐：

```css
border-top: 0;
font: 100%/1.6 palatino, georgia, serif;
padding: 0 1em 2em;
```

#### 1.3.4 每个选择器及属性独占一行

不推荐：

```css
button {
  width: 100px;
  height: 50px;
  color: #fff;
  background: #00a0e9;
}
```

推荐：

```css
button {
  width: 100px;
  height: 50px;
  color: #fff;
  background: #00a0e9;
}
```

#### 1.3.5 省略 0 后面的单位；如遇到 0.x 的值，建议写全，不建议省略 0.

不推荐：

```css
div {
  padding-bottom: 0px;
  margin: 0em;
  padding-left: 0.1px;
}
```

推荐：

```css
div {
  padding-bottom: 0;
  margin: 0;
  padding-left: 0.1px;
}
```

#### 1.3.6 避免使用 ID 选择器及全局标签选择器防止污染全局样式

不推荐：

```css
#header {
  padding-bottom: 0px;
  margin: 0em;
}
```

推荐：

```css
.header {
  padding-bottom: 0px;
  margin: 0em;
}
```

### (四) SASS 规范

#### 1.4.1 代码组织

##### 1) 将公共 sass 文件放置在 style / sass / common 文件夹

#### 1.4.2 避免嵌套层级过多

将嵌套深度限制在 3 级。对于超过 4 级的嵌套，给予重新评估。这可以避免出现过于详实的 CSS 选择器。
避免大量的嵌套规则。当可读性受到影响时，将之打断。推荐避免出现多于 20 行的嵌套规则出现

不推荐：

```css
.main {
  .title {
    .name {
      color: #fff;
    }
  }
}
```

推荐：

```css
.main-title {
  .name {
    color: #fff;
  }
}
```

#### 1.4.3 特殊规范

- 对用页面级组件样式，应该是有作用域的

- 对于公用组件或者全局组件库，我们应该更倾向于选用基于 class 的 BEM 策略

  ```javascript
    <style lang='scss'></style> // bad

    <!-- 使用 scoped 作用域 -->
    <style lang='scss' scoped></style> // good

    <!-- 使用 BEM 约定 -->
    <style> // good
    .c-Button {
      border: none;
      border-radius: 2px;
    }

    .c-Button--close {
      background-color: red;
    }
    </style>

  ```

### (五) Javascript 规范

#### 1.5.1 命名

##### 1) 采用小写驼峰命名 lowerCamelCase，代码中的命名均不能以下划线，也不能以下划线或美元符号结束

反例： `_name / name_ / name$`

##### 2) 方法名、参数名、成员变量、局部变量都统一使用 lowerCamelCase 风格，必须遵从驼峰形式。

正例： `localValue / getHttpMessage() / inputUserId`

**其中 method 方法命名必须是 动词 或者 动词+名词 形式**

正例：`saveShopCarData /openShopCarInfoDialog`

反例：`save / open / show / go`

**特此说明，增删查改，详情统一使用如下 5 个单词，不得使用其他（目的是为了统一各个端）**

```
add / update / delete / detail / get
```

> 建议：vue template 内的事件方法名以 `handle` 开头，eg: `handleSave`, 以区分是事件还是普通方法；

**附： 函数方法常用的动词:**

```
get 获取/set 设置,
add 增加/remove 删除
create 创建/destory 移除
start 启动/stop 停止
open 打开/close 关闭,
read 读取/write 写入
load 载入/save 保存,
begin 开始/end 结束,
backup 备份/restore 恢复
import 导入/export 导出,
split 分割/merge 合并
inject 注入/extract 提取,
attach 附着/detach 脱离
bind 绑定/separate 分离,
view 查看/browse 浏览
edit 编辑/modify 修改,
select 选取/mark 标记
copy 复制/paste 粘贴,
undo 撤销/redo 重做
insert 插入/delete 移除,
add 加入/append 添加
clean 清理/clear 清除,
index 索引/sort 排序
find 查找/search 搜索,
increase 增加/decrease 减少
play 播放/pause 暂停,
launch 启动/run 运行
compile 编译/execute 执行,
debug 调试/trace 跟踪
observe 观察/listen 监听,
build 构建/publish 发布
input 输入/output 输出,
encode 编码/decode 解码,
encrypt 加密/decrypt 解密,
compress 压缩/decompress 解压缩
pack 打包/unpack 解包,
parse 解析/emit 生成,
connect 连接/disconnect 断开,
send 发送/receive 接收,
download 下载/upload 上传,
refresh 刷新/synchronize 同步,
update 更新/revert 复原,
lock 锁定/unlock 解锁,
check out 签出/check in 签入,
submit 提交/commit 交付,
push 推/pull 拉,
expand 展开/collapse 折叠,
begin 起始/end 结束,
start 开始/finish 完成,
enter 进入/exit 退出,
abort 放弃/quit 离开,
obsolete 废弃/depreciate 废旧,
collect 收集/aggregate 聚集
```

##### 3) 常量命名全部大写，单词间用下划线隔开，力求语义表达完整清楚，不要嫌名字长。

正例： `MAX_STOCK_COUNT`

反例： `MAX_COUNT`

#### 1.5.2 代码格式

##### 1) 使用 2 个空格进行缩进

正例：

```javascript
if (x < y) {
  x += 10;
} else {
  x += 1;
}
```

##### 2) 不同逻辑、不同语义、不同业务的代码之间插入一个空行分隔开来以提升可读性。

> 说明：任何情形，没有必要插入多个空行进行隔开。

#### 1.5.3 字符串

统一使用单引号(‘)，不使用双引号(“)。这在创建 HTML 字符串非常有好处：

正例:

```javascript
let str = "foo";
let testDiv = '<div id="test"></div>';
```

反例：

```javascript
let str = "foo";
let testDiv = "<div id='test'></div>";
```

#### 1.5.4 对象声明

##### 1) 使用字面值创建对象

正例： `let user = {};`

反例： `let user = new Object();`

##### 2) 使用字面量来代替对象构造器

正例：

```javascript
var user = {
  age: 0,
  name: 1,
  city: 3,
};
```

反例：

```
var user = new Object();
user.age = 0;
user.name = 0;
user.city = 0;
```

#### 1.5.5 变量声明

使用`const`,`let` 声明变量， 少用`var`；

#### 1.5.6 严格相等

用“===”, '!=='代替'==', '!='；避免 javaScript 隐式类型转换；

#### 1.5.5 使用 ES6,ES7

必须优先使用 ES6,ES7 中新增的语法糖和函数。这将简化你的程序，并让你的代码更加灵活和可复用。

> 必须强制使用 ES6, ES7 的新语法，比如箭头函数、await/async，解构，let，for…of 等等

#### 1.5.6 括号

下列关键字后必须有大括号（即使代码块的内容只有一行）：if, else, for, while, do, switch, try, catch, finally, with。

正例：

```javascript
if (condition) {
  doSomething();
}
```

反例：

```
if (condition) doSomething();
```

#### 1.5.7 undefined 判断

永远不要直接使用 `undefined` 进行变量判断；使用 typeof 和字符串 `'undefined'` 对变量进行判断。

正例：

```javascript
if (typeof person === 'undefined') {
    ...
}
```

反例：1

```javascript
// person 为 null 也是 true
if (person == undefined) {
    ...
}
```

反例：2

```javascript
if (person === undefined) {
    ...
}

// JavaScript 设计问题， undefined 可以全局作用域中被当作标识符（变量名）来使用
// 因为 undefined 不是一个保留字
// 不要这样做！

// 打印 'foo string' PS：说明undefined的值和类型都已经改变
(function() {
var undefined = 'foo';
console.log(undefined, typeof undefined)
})()

// 打印 'foo string' PS：说明undefined的值和类型都已经改变
(function(undefined) {
console.log(undefined, typeof undefined)
})('foo')
```

#### 1.5.8 条件判断和循环最多三层

条件判断能使用三目运算符和逻辑运算符解决的，就不要使用条件判断，但是谨记不要写太长的三目运算符。如果超过 3 层请抽成函数，并写清楚注释。

#### 1.5.9 this 的转换命名

对上下文 `this` 的引用只能使用 `self` 来命名

#### 1.5.10 慎用 `console.log`

因 `console.log` 大量使用会有性能问题，所以在非 webpack 项目中谨慎使用 log 功能。正式环境应去除无用 `console`;

#### 1.5.11 空格

- 关键字前后留空格。

- 对象的值前面留空格。

- 操作符前后留空格。

- 逗号后面留空格。

- 大括号中前后留空格。

## 二、Vue 项目规范

### (一) Vue 编码基础

二、Vue 项目规范以 Vue 官方规范 （https://cn.vuejs.org/v2/style-guide/） 中的 A 规范为基础，在其上面进行项目开发，故所有代码均遵守该规范。

> 请仔仔细细阅读 Vue 官方规范，切记，此为第一步。

#### 2.1.1. 组件规范

##### 1) 组件名为多个单词。

组件名应该始终是多个单词组成（大于等于 2），且命名规范为 `KebabCase` 格式。
这样做可以避免跟现有的以及未来的 HTML 元素相冲突，因为所有的 HTML 元素名称都是单个单词的。

正例：

```javascript
export default {
  name: "TodoItem",
  // ...
};
```

反例：

```javascript
export default {
  name: "Todo",
  // ...
};
export default {
  name: "todo-item",
  // ...
};
```

##### 2) 组件文件名为 pascal-case 格式

正例：

```Code
components/
|- my-component.vue
```

反例：

```
components/
|- myComponent.vue
|- MyComponent.vue
```

##### 3) 基础组件文件名为 base 开头，使用完整单词而不是缩写。

正例：

```
components/
|- base-button.vue
|- base-table.vue
|- base-icon.vue
```

反例：

```
components/
|- MyButton.vue
|- VueTable.vue
|- Icon.vue
```

##### 4) 和父组件紧密耦合的子组件应该以父组件名作为前缀命名

正例：

```
components/
|- todo-list.vue
|- todo-list-item.vue
|- todo-list-item-button.vue
|- user-profile-options.vue （完整单词）
```

反例：

```
components/
|- TodoList.vue
|- TodoItem.vue
|- TodoButton.vue
|- UProfOpts.vue （使用了缩写）
```

##### 5) 在 Template 模版中使用组件，应使用 PascalCase 模式，并且使用自闭合组件。

正例：

```html
<!-- 在单文件组件、字符串模板和 JSX 中 -->
<MyComponent />
<Row><table :column="data" /></Row>
```

反例：

```html
<my-component /> <row><table :column="data" /></row>
```

##### 6) 组件的 data 必须是一个函数

当在组件中使用 data 属性的时候 (除了 new Vue 外的任何地方)，它的值必须是返回一个对象的函数。 因为如果直接是一个对象的话，子组件之间的属性值会互相影响。

正例：

```javascript
export default {
  data() {
    return {
      name: "jack",
    };
  },
};
```

反例：

```javascript
export default {
  data: {
    name: "jack",
  },
};
```

##### 7) Prop 定义应该尽量详细

- 必须使用 camelCase 驼峰命名
- 必须指定类型
- 必须加上注释，表明其含义
- 必须加上 required 或者 default，两者二选其一
- 如果有业务需要，必须加上 validator 验证

正例：

```javascript
 props: {
  // 组件状态，用于控制组件的颜色
   status: {
     type: String,
     required: true,
     validator: function (value) {
       return [
         'succ',
         'info',
         'error'
       ].indexOf(value) !== -1
     }
   },
    // 用户级别，用于显示皇冠个数
   userLevel：{
      type: String,
      required: true
   }
}
```

##### 8) 在声明 prop 的时候，其命名应该始终使用 camelCase，而在模板中应该始终使用 `kebab-case`

正例：

```javascript
props: {
  greetingText: String;
}
<WelcomeMessage greeting-text="hi" />;
```

反例：

```javascript
props: {
  'greeting-text': String
}
<WelcomeMessage greetingText="hi"/>
```

##### 9) 为组件样式设置作用域

正例：

```html
<template>
  <button class="btn btn-close">X</button>
</template>

<!-- 使用 `scoped` 特性 -->
<style scoped>
  .btn-close {
    background-color: red;
  }
</style>
```

反例：

```html
<template>
  <button class="btn btn-close">X</button>
</template>
<!-- 没有使用 `scoped` 特性 -->
<style>
  .btn-close {
    background-color: red;
  }
</style>
```

##### 10) 如果特性元素较多，应该主动换行。单行代码不和超过 120

正例：

```html
<MyComponent foo="a" bar="b" baz="c" msg="d" name="e" />
```

反例：

```html
<MyComponent foo="a" bar="b" baz="c" msg="d" name="e" />
```

##### 11）模板事件名

事件方法推荐以 `handleXXX`， 自定义事件应避免使用 `onXXX`;

正例：

```html
<button @click="handleClick">点我</button>

<MyComponent @open>这是一个组件</MyComponent>

<script>
  this.$emit("open", payload);
</script>
```

反例：

```html
<button @click="onClick">点我</button>

<MyComponent @open>这是一个组件</MyComponent>
<script>
  this.$emit("onOpen", payload);
</script>
```

#### 2.1.2. 模板中使用简单的表达式

组件模板应该只包含简单的表达式，复杂的表达式则应该重构为计算属性或方法。复杂表达式会让你的模板变得不那么声明式。我们应该尽量描述应该出现的是什么，而非如何计算那个值。而且计算属性和方法使得代码可以重用。

正例：

```html
<template>
  <p>{{ normalizedFullName }}</p>
</template>

<script>
  // 复杂表达式已经移入一个计算属性
  computed: {
    normalizedFullName: function () {
      return this.fullName.split(' ').map(function (word) {
        return word[0].toUpperCase() + word.slice(1)
      }).join(' ')
    }
  }
</script>
```

反例：

```html
<template>
  <p>
    {{ fullName.split(' ').map(function (word) { return word[0].toUpperCase() +
    word.slice(1) }).join(' ') }}
  </p>
</template>
```

#### 2.1.3 指令都使用缩写形式

指令推荐都使用缩写形式，(用 : 表示 v-bind: 、用 @ 表示 v-on: 和用 # 表示 v-slot:)

正例：

```html
<input @input="onInput" @focus="onFocus" />
```

反例：

```html
<input v-on:input="onInput" @focus="onFocus" />
```

#### 2.1.4 标签顺序保持一致

单文件组件应该总是让`<template>` 、`<script>`和 `<style>` 标签的顺序保持一致。

正例：

```html
<template>...</template>
<script>
  ...
</script>
<style>
  ...;
</style>
```

反例：

```html
<template>...</template>
<style>
  ...;
</style>
<script>
  ...
</script>
```

#### 2.1.5 合理的使用键值 key

1. 必须为 v-for 设置键值 key 且避免直接使用索引

2. **如果一组 `v-if` + `v-else` 的元素类型相同，最好使用 `key` (比如两个 `<div>` 元素)。**

默认情况下，Vue 会尽可能高效的更新 DOM。这意味着其在相同类型的元素之间切换时，会修补已存在的元素，而不是将旧的元素移除然后在同一位置添加一个新元素。

正例：

```html
<div v-if="error" key="search-status">错误：{{ error }}</div>
<div v-else key="search-results">{{ results }}</div>
```

反例：

```html
<div v-if="error">错误：{{ error }}</div>
<div v-else>{{ results }}</div>
```

#### 2.1.6 v-show 与 v-if 选择

如果运行时，需要非常频繁地切换，使用 v-show ；如果在运行时，条件很少改变，使用 v-if。

#### 2.1.7 script 标签内部结构顺序

name > components > props > data > computed > watch > filter > 钩子函数（钩子函数按其执行顺序） > methods

#### 2.1.8 Vue Router 规范

##### 1) 页面跳转数据传递使用路由参数

页面跳转，例如 A 页面跳转到 B 页面，需要将 A 页面的数据传递到 B 页面，推荐使用 路由参数进行传参，而不是将需要传递的数据保存 vuex，然后在 B 页面取出 vuex 的数据，因为如果在 B 页面刷新会导致 vuex 数据丢失，导致 B 页面无法正常显示数据。

正例：

```javascript
let id = " 123";
this.$router.push({ name: "userCenter", query: { id: id } });
```

##### 2) 使用路由懒加载（延迟加载）机制

```javascript
{
    path: '/uploadAttachment',
    name: 'uploadAttachment',
    meta: {
      title: '上传附件'
    },
    component: () => import('@/view/components/uploadAttachment/index.vue')
  },
```

##### 3) router 中的命名规范

path、childrenPoints 命名规范采用 `kebab-case` 命名规范（尽量 Vue 文件的目录结构保持一致，因为目录、文件名都是 `kebab-case`，这样很方便找到对应的文件）

name 命名规范采用 `KebabCase` 命名规范且和 component 组件名保持一致！（**因为要保持 keep-alive 特性，keep-alive 按照 component 的 name 进行缓存，所以两者必须高度保持一致**）

```javascript
// 动态加载
export const reload = [
  {
    path: "/reload",
    name: "reload",
    component: Main,
    meta: {
      title: "动态加载",
      icon: "icon iconfont",
    },

    children: [
      {
        path: "/reload/smart-reload-list",
        name: "SmartReloadList",
        meta: {
          title: "SmartReload",
          childrenPoints: [
            {
              title: "查询",
              name: "smart-reload-search",
            },
            {
              title: "执行reload",
              name: "smart-reload-update",
            },
            {
              title: "查看执行结果",
              name: "smart-reload-result",
            },
          ],
        },
        component: () =>
          import("@/views/reload/smart-reload/smart-reload-list.vue"),
      },
    ],
  },
];
```

##### 4) router 中的 path 命名规范

path 除了采用 `kebab-case` 命名规范以外，必须以 / 开头，即使是 children 里的 path 也要以 / 开头。如下示例

目的：

经常有这样的场景：某个页面有问题，要立刻找到这个 vue 文件，如果不用以/开头，path 为 parent 和 children 组成的，可能经常需要在 router 文件里搜索多次才能找到，而如果以 / 开头，则能立刻搜索到对应的组件

```javascript
{
    path: '/file',
    name: 'File',
    component: Main,
    meta: {
      title: '文件服务',
      icon: 'ios-cloud-upload'
    },
    children: [
      {
        path: '/file/file-list',
        name: 'FileList',
        component: () => import('@/views/file/file-list.vue')
      },
      {
        path: '/file/file-add',
        name: 'FileAdd',
        component: () => import('@/views/file/file-add.vue')
      },
      {
        path: '/file/file-update',
        name: 'FileUpdate',
        component: () => import('@/views/file/file-update.vue')
      }
    ]
  }
```

### (二) Vue 项目目录规范

#### 2.2.1 基础

vue 项目中的所有命名一定要与后端命名统一。

比如权限：后端 auth, 前端无论 router , store, api 等都必须使用 auth 单词！

后端一些自定义 http 状态码含义， 如：没有权限。登陆认证失效等；

#### 2.2.2 使用 Vue-cli 脚手架（暂定，公司目前有 adminBase）

使用 vue-cli3 来初始化项目，项目名按照上面的命名规范

#### 2.2.3 目录说明（以 adminBase 为例）

```shell
├── build 															# 编译构建相关文件
└── dist 																# 打包输出目录
└── docs  															# 文档目录
└── env                                 # 项目级变量配置文件目录
└── public  														# 公共资源目录（静态）
src																			# 源码目录
├── api																	# 所有api接口
├── assets															# 静态资源
├── component														# 自定义基础组件
├── components													# 统一研发平台组件
├── i18n																# 国际化
├── icons																# 图标
├── layout															# 布局相关
├── mixins															# 混入
├── router															# 路由
├── store																# vuex
├── styles															# sass 样式文件
├── utils																# 工具类
└── views																# 页面文件
```

### 图片使用

Data URIs（base64 编码）
优点：

1. 减少请求数
2. 现有项目编译方式下利于代码变编写

缺点：

1. 转换文件体积大，大约比原始的二进制大 33%
2. 图片显示相对较慢，需要更多的 CPU 消耗
3. IE6 / IE7 不支持

建议使用：

1. 对于静态图片，如非常小的 icon，可以建议 ui 合成雪碧图，放置于 static 目录下的图片文件夹下，通过相对路径引入，配合 webpack 配置，这将不会再对图片进行 base64 编译。
2. 对于特别大的静态图片（此处暂定为 5kb 以上，可以根据具体情况调整），建议配个编译工具进行压缩，如 webpack 下的 image-webpack-loader
3. 其余中等大小的图片，可以直接使用 Data URIs 方式
4. 移动端下一律不使用 Data URIs

```css
/* CSS */
.test {
  background-color: red;
  background-repeat: no-repeat;
  background-image: url(/img/icon.png);
  background-position: 0 0;
}

/* SCSS */
.test {
  background: {
    color: red;
    repeat: no-repeat;
    image: url(/img/icon.png);
    position: 0 0;
  }
}

/* CSS */
.test {
}
.test_cover {
}
.test_info {
}
.test_info_name {
}

/* SCSS */
.test {
  &_cover {
  }
  &_info {
    &_name {
    }
  }
}
```

​ 图片使用建议： 建议大图统一上传到阿里 OSS。 不仅可以减少服务器资源占用，也会提高页面响应速度；

> 建议： 目前发现我们的项目中的 `iconfont` 采用的全是图片载入的方式， 建议 UI 可以打造一套属于我们自己公司常用业务的风格的`iconfont`库；

#### 2.2.4 注释说明

整理必须加注释的地方

- 公共组件使用说明
- api 目录的接口 js 文件必须加注释
- store 中的 state, mutation, action 等必须加注释
- vue 文件中的 template 必须加注释，若文件较大添加 start end 注释
- vue 文件的 methods，每个 method 必须添加注释
- vue 文件的 data, 非常见单词要加注释

#### 2.2.5 其他

##### 1) 尽量不要手动操作 DOM

因使用 vue 框架，所以在项目开发中尽量使用 vue 的数据驱动更新 DOM，尽量（不到万不得已）不要手动操作 DOM，包括：增删改 dom 元素、以及更改样式、添加事件等。

##### 2) 删除无用代码

因使用了 git/svn 等代码版本工具，对于无用代码必须及时删除，例如：一些调试的 console 语句、无用的弃用功能代码。

## 三、 编辑器约定

#### 统一使用 vscode 编辑器

旨在统一前端代码风格建议统一使用 vscode 编辑器；

推荐几个我觉得不错的插件：

- Vetur 开发 vue 必备

- Eslint 代码风格检查

- Stylelint CSS/SCSS/Less 检测工具

- GitLens git 代码日志

- Chinese (Simplified) Language Pack for VS Code (vscode 中文语言包，适合英文差的同鞋)

- Prettier Visual Studio 代码的更漂亮的格式化程序

- Auto Close Tag 自动添加 HTML/XML 关闭标签

- Bracket Pair ColorZer (颜色识别匹配括号)

- Auto Rename Tag 自动重命名配对的标签

- DotENV

- Git History

- Live Server

- Vscode-icons

- Path Intellisense 路径自动补全

- I18n Ally 国际化插件

  > vscode 统一配置参考: 我自己的配置 | 待优化

  ```json
  {
    "files.eol": "\n",
    "search.exclude": {
      "**/node_modules": true
    },
    "editor.formatOnSave": true,
    // "editor.defaultFormatter": "esbenp.prettier-vscode",
    "gitlens.advanced.messages": {
      "suppressFileNotUnderSourceControlWarning": true,
      "suppressShowKeyBindingsNotice": true
    },
    "editor.renderWhitespace": "boundary", // 在边界处渲染空格
    "editor.rulers": [120], // 在120个字符处显示一条竖线
    "window.zoomLevel": 0,
    "editor.insertSpaces": false,
    "explorer.autoReveal": true,
    // "vetur.validation.template": false,
    "vetur.completion.scaffoldSnippetSources": {
      // "workspace": "💼",
      // "user": "🗒️",
      // "vetur": "✌"
    },
    "vetur.experimental.templateInterpolationService": false,
    "files.associations": {
      "*.wpy": "vue",
      "*.cjson": "jsonc",
      "*.wxss": "css",
      "*.wxs": "javascript",
      "*.wya": "vue"
    },
    "eslint.validate": [
      "javascript",
      "javascriptreact",
      "typescript",
      "vue",
      "typescriptreact"
    ],
    "editor.snippetSuggestions": "top",
    "editor.tabCompletion": "on",
    "javascript.updateImportsOnFileMove.enabled": "always",
    "emmet.includeLanguages": {
      "wxml": "html",
      "javascript": "javascriptreact"
    },
    "minapp-vscode.disableAutoConfig": true,
    "editor.accessibilitySupport": "off",
    "explorer.confirmDelete": false,
    // "workbench.colorTheme": "Material Theme High Contrast",
    "workbench.iconTheme": "vscode-icons",
    "vsicons.dontShowNewVersionMessage": true,
    "explorer.confirmDragAndDrop": false,
    "[javascript]": {
      "editor.defaultFormatter": "vscode.typescript-language-features"
    },
    "[json]": {
      "editor.defaultFormatter": "vscode.json-language-features"
    },
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true
    },
    "[wxml]": {
      "editor.defaultFormatter": "qiu8310.minapp-vscode"
    },
    "workbench.settings.useSplitJSON": true,
    "files.autoSaveDelay": 1500,
    "timeline.excludeSources": [],
    "files.autoSave": "onFocusChange",
    "emmet.excludeLanguages": ["markdown"],
    "eslint.codeAction.showDocumentation": {
      "enable": true
    },
    "editor.fontSize": 14,
    "diffEditor.ignoreTrimWhitespace": false,
    "terminal.integrated.shell.osx": "/bin/zsh",
    "vetur.format.defaultFormatterOptions": {
      "js-beautify-html": {
        "wrap_attributes": "force-expand-multiline"
      },
      "prettyhtml": {
        "printWidth": 100,
        "singleQuote": true,
        "wrapAttributes": false,
        "sortAttributes": false
      }
    },
    "vetur.ignoreProjectWarning": true,
    "editor.largeFileOptimizations": false,
    "auto-close-tag.activationOnLanguage": [
      "xml",
      "php",
      "blade",
      "ejs",
      "jinja",
      "javascript",
      "javascriptreact",
      "typescript",
      "typescriptreact",
      "plaintext",
      "markdown",
      "vue",
      "liquid",
      "erb",
      "lang-cfml",
      "cfml",
      "HTML (EEx)",
      "HTML (Eex)",
      "plist"
    ],
    "markdownlint.config": {
      "no-hard-tabs": false,
      "list-marker-space": false,
      "single-title": false
    },
    "editor.tabSize": 2,
    "vetur.validation.template": false,
    "i18n-ally.displayLanguage": "zh",
    "[html]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "liveServer.settings.donotShowInfoMsg": true
  }
  ```

  #### 及时处理控制台提示和错误

  代码提交前 **必须** 解决掉 eslist 的提示错误和警告, 删除掉测试代码和无用的 `console` 包证上传到仓库的代码是干净和没有错误的；

  #### 单行代码不超过 120

  元素属性合理换行，尽量不超过 120，像一些正则表达式除外。

  Vscode settings.json 可配置

  ```
  "editor.rulers": [120], // 在120个字符处显示一条竖线以做参考
  ```

  #### 编写合适项目的代码片段插件 TODO

## 四、git 规范

一个项目都是由很多人一起合作，然而每个人的开发习惯，提交格式并不统一，这对于统计 bug 和 需求有一定困难。 所以，commit message 规范就格外重要。

**commit message 的格式**

> 类别: 做了什么 简短描述做了什么
>
> 详细描述做了什么（可省略）

| type     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| feat     | 新功能、新需求                                               |
| fix      | 修复一个 bug                                                 |
| docs     | 更新文档                                                     |
| style    | 格式和代码无关                                               |
| refactor | 重构（既不是新增，也不是代码变动）                           |
| test     | 增加测试                                                     |
| chore    | 构建过程中或辅助工具的变动                                   |
| perf     | 改善性能                                                     |
| build    | 变更项目构建或外部依赖（例如 scopes: webpack、gulp、npm 等） |
| ci       | 更改持续集成软件的配置文件和 package 中的 scripts 命令       |
| revert   | 代码回退                                                     |

**详见 git flow 流程**

**唯一要求**：每天下班前提交当日新增的代码，每日上班的时候同步代码；遇到合并代码起冲突时一定要找对应开发确认后再合并避免盲目合并带来 bug;

## 五、构建规范

1. 线上环境，必须清除 console

2. 解决冲突后提交 mr，由 owner review

3. owner 必须 review 上线代码

4. bug fix 更新小版本号

5. 需求功能迭代更新中版本号

6. 大面积重构，推翻重写，更新大版本号

7. 在打包的同时生成版本信息管理文本便于版本维护。

   下面是代码 version.js 【程序包】

   ```javascript
   /* eslint-disable max-len */
   const execSync = require("child_process").execSync; // 同步子进程
   const fs = require("fs");

   const versionPath = "version.txt"; // version路径
   const buildPath = "dist"; // 打包的路径
   const autoPush = true; // 写入版本信息之后是否自动提交git上
   const commitHash = execSync("git show -s --format=%H").toString().trim(); // 最后提交的版本hash
   const gitRemteAddress = execSync("git remote -v")
     .toString()
     .split("\n")[0]
     .split("\t")[1];
   let versionStr = ""; // 版本信息字符串

   // 如果versionPath存在，将先读取里边的版本信息
   if (fs.existsSync(versionPath)) {
     versionStr = fs.readFileSync(versionPath).toString() + "\n";
   }

   if (versionStr.indexOf(commitHash) != -1) {
     console.warn(
       "\x1B[33m%s\x1b[0m",
       "warming: 当前的git版本数据已经存在了!\n"
     );
   } else {
     // git 最后一次提交的 HEAD
     const commitUserName = execSync("git show -s --format=%cn")
       .toString()
       .trim();
     const commitUserEmail = execSync("git show -s --format=%ce")
       .toString()
       .trim();
     const commitMessage = execSync("git show -s --format=%s")
       .toString()
       .trim();
     const branch = execSync("git name-rev --name-only HEAD").toString().trim();
     const commitDateObj = new Date(
       execSync("git show -s --format=%cd").toString()
     );
     const commitDate = `${
       commitDateObj.getFullYear() +
       "-" +
       (commitDateObj.getMonth() + 1) +
       "-" +
       commitDateObj.getDate() +
       " " +
       commitDateObj.getHours() +
       ":" +
       commitDateObj.getMinutes()
     }`;
     const buildUserName = execSync("git config user.name").toString().trim();
     const buildUserEmail = execSync("git config user.email").toString().trim();
     const nowDate = new Date();
     const buildDate = `${
       nowDate.getFullYear() +
       "-" +
       (nowDate.getMonth() + 1) +
       "-" +
       nowDate.getDate() +
       " " +
       nowDate.getHours() +
       ":" +
       nowDate.getMinutes()
     }`;
     versionStr = `
   		commitHash: ${commitHash}
   		commitUserName: ${commitUserName}
   		commitUserEmail: ${commitUserEmail}
   		commitMessage: ${commitMessage}
   		commitDate: ${commitDate}
   		gitRemoteAddress: ${gitRemteAddress}
   		buildUserName: ${buildUserName}
   		buildUserEmail: ${buildUserEmail}
   		buildBranch: ${branch}
   		buildDate: ${buildDate}
   		\n${new Array(80).join("*")}
   		`;

     fs.writeFileSync(versionPath, versionStr, {
       flag: "a",
     });
     // 写入版本信息之后，自动将版本信息提交到当前分支的git上
     if (autoPush) {
       execSync(`git add ${versionPath}`);
       execSync(`git commit ${versionPath} -m "docs: 自动提交版本信息"`);
       execSync(`git push origin ${branch}`);
     }
   }

   // 将version文件移植到打包文件中
   if (fs.existsSync(buildPath)) {
     fs.writeFileSync(
       `${buildPath}/${versionPath}`,
       fs.readFileSync(versionPath)
     );
   }

   console.info(
     "\x1B[32m%s\x1b[0m",
     [
       "::::::::  :::    :::  ::::::::   ::::::::  :::::::::: ::::::::   ::::::::  ",
       ":+:    :+: :+:    :+: :+:    :+: :+:    :+: :+:       :+:    :+: :+:    :+: ",
       "+:+        +:+    +:+ +:+        +:+        +:+       +:+        +:+        ",
       "+#++:++#++ +#+    +:+ +#+        +#+        +#++:++#  +#++:++#++ +#++:++#++ ",
       "       +#+ +#+    +#+ +#+        +#+        +#+              +#+        +#+ ",
       "#+#    #+# #+#    #+# #+#    #+# #+#    #+# #+#       #+#    #+# #+#    #+# ",
       " ########   ########   ########   ########  ########## ########   ########  ",
     ].join("\n")
   );
   ```

   ```shell
   # 修改打包脚本 追加 '&& node version.js'
   "scripts": {
           "build": "vue-cli-service build --mode production --dest dist && node version.js",
       },
   ```

## 六、CI/CD & Docker + jenkins

TODO
