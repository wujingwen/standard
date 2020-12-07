# 前端代码规范

## 开发工具
* Hbuilder
```
  搭配uni-app框架使用，用于开发小程序相关
```

* VS code
```
  用于web页面开发。必须安装插件Eslint
```

缩进符必须为两个空格

## 命名相关

一、 文件目录命名
```
  * 通常目录命名（多个单词）采用中划线法，例如：@views/error-pages
  * components目录下采用Pascal命名法，例如：@/components/DragSelect
```

二、 html命名
```
  * html文件命名（多个单词）采用中划线法，例如：address-edit
```

三、css命名
```
  * css文件命名（多个单词）采用中划线法，例如：@/styles/element-variables;

  * class命名采用BEM规范，block__element--modifier，通常每个类名中element只会出现一次，不可出现多个，如button__primary--success;

  * BEM命名法最多只能出现两层，如home__banner，不可出现如home__banner__img

  * 单个block或element的命名可使用中划线，如submit-button__primary--success
```

四、vue相关命名
```
  * vue文件命名（多个单词）在view级文件上采用中划线命名法，除了index.vue,例如：address-edit.vue

  * vue文件命名（多个单词）在组件级文件上采用中Pascal命名法，例如：KeyBoard.vue

  * data中变量定义使用驼峰命名法，例如：listData

  * 组件必须使用中划线命名，重用组件推荐以Item结尾，例如：name-card-item

  * 引入组件必须使用Pascal命名，如: import NameCardItem from 'NameCardItem'

  * 使用自定义组件必须使用Pascal标签，如<NameCardItem></NameCardItem>，用以区分自定义组件以及第三方UI库组件

  * store中state/getters/action使用驼峰命名法，例如getWeiXinData

  * store中mutation中使用全部大写的下划线命名法，例如：SET_TITLE

  * eventBus所有listener使用全部大写的下划线命名法，例如：SET_TITLE

  * axios方法以get、post、fetch开头，并根据后端接口名命名，例如：后端接口：/api/news_list 即可定义名称  为: fetchNewsList

  * methods方法中推荐使用set、get、open、close、jump、load等开始动词,并且必须驼峰命名,例如：initPage () {}，若方法由用户手动触发，则必须以handle开头，如handleClick

  * data数据中带有判断性质的变量必须使用is（是否）、has（是否含有）、can（是否能够）等动词命名，例如：isShowPopup

  * 所有常量必须使用全部大写的下划线命名法，和mutation一致，例如：MAX_COUNT

  * 定义props参数必须使用props验证形式，例如：name {type: String | Number, default: 'Ivan'}

  * router路由中路径名称必须使用中划线命名法，例如：public-home
```

五、图片命名
```
  * 采用下划线命名法，如home_banner.png

  * 如果是图标，则采用icon_开头，如icon_close.png 
```

## 注释相关

> 注释模板可使用自定义代码块实现

一、html注释

```javascript
 <!-- ============== 这是注释 ============== -->
```

二、css注释

```javascript
 /* 这是块状注释 */
```

三、js注释
```javascript
 // 注释1（必须空格处理）

 /* 注释2 */

 /**
  * @Description: 注释三
  * @param 
  * @return 
  */
```

```
  * props以及data中，所有变量必须添加注释
  * props以及data中，变量优先使用行内注释，与变量同行
  * 行内注释必须空格处理，例如：// 这是注释
  * 具体涉及到逻辑注释，使用单行注释
  * 具体涉及到逻辑总结注释，使用块状注释（注释二）
  * 函数（方法）或者必须要多行注释（注释三），且必须空行处理，而且每个参数需要表明具体注释
```

## 书写格式
```
  * common.scss中抽取了常用的样式，调用这些公用样式以减少代码冗余

  * css书写中，每个selector之间必须空行处理

  * data中的每个数据必须做空行处理，必须添加行内注释

  * 每个method必须添加注释，标注每个参数的作用，并且空行处理

  * 其余格式通过eslint作出限制
```

## 代码优化相关
```
  * 书写js代码均使用es6语法

  * 对于判断,推荐层级：短路运算 > 三目运算 > switch/case > if/else

  * 使用vue构建的项目，页面中export的书写顺序应为:
    - name
    - mixins
    - components   
    - props    
    - data
    - filter
    - watch 
    - computed    
    - created
    - beforeMount
    - mounted
    - beforeUpdate
    - updated
    - activited
    - deactivated
    - beforeDestroy
    - destroyed
    - metods   

  * 使用uni-app构建的项目，页面中export的书写顺序应为:
    - name
    - mixins
    - components   
    - props    
    - data
    - filter
    - watch 
    - computed      
    - onLoad
    - onShow
    - onReady
    - onUnload
    - metods   

  * 若页面功能相对复杂，可按照功能分成若干组件。若某功能为全局公用或频繁调用，则抽取为公用组件
```

## 性能优化相关
```
  * 尽可能避免使用js进行页面布局。（重点） 

  * 相关动画尽可能使用CSS3编写而非js。（重点）

  * 如需完成复杂的自定义动画，尽可能避免使用gif，可联系UI将其处理成json引入

  * 能不用图片就不要使用图片，可配合UI使用iconfont,或者代码实现

  * 定义全局（公共）和局部（页面内），views和css(scss)

  * 推荐组件、图片懒加载处理
```
