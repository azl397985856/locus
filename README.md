# Intro
分析用户行为轨迹数据，并将分析的数据生成json文件。

# Motivation
我做这个项目的原因是，希望可以做一个”自产自销“的一个app。 如何理解“自产自销”呢？大概的原理可以用下图来描述：
![self consume](https://github.com/azl397985856/locus/blob/master/locusxml.png)

用户在使用我的app 的时候，我会收集用户的数据信息，然后将数据信息上报，然后集中处理（locus处理），生成一个json 文件，该文件又可以被app
直接消费。 消费的结果是什么呢？   就是app 可以针对用户的操作习惯做一些优化处理，最典型的就是资源预加载。
因此我打算在第一版本先做这个功能，后续可能会加入智能推送等业务。
我的目标是，app 可以不用自己处理类似这样的数据和逻辑，就可以享受到更佳的用户体验（智能预加载等）
# What does it do
用户上报的数据会被组织成**数组**，然后交给locus处理，生成供app消费的**json数据** .
大概是这样子：
```js

[{userId: 'karl', locus: ['Page A', 'Page C', 'Page F'], category: 'teacher'},
{userId: 'karl', locus: ['Page A', 'Page B', 'Page D'], category: 'student'}]
 ->
 {
     raw : preload.json
     grouped: preload.json
     persernalize: preload.json
 }
 
 // preload.json
 {
    'Page A' : {
      'Page C': 50%,
      'Page B': 50%
    },
    'Page C' : {
      'Page F': 100%
    },
    'Page B' : {
      'Page D': 100%
    }
 }
 
```

这里写成Page X   只是方便理解，其实应该是Component X，  也就是说粒度会更小，我们会做到组件层级上。
组件划分的粒度越精确，带来的用户收益就越高。

数据怎么用呢？
app  可以根据 页面 间跳转的意愿程度，决定提前渲染不同的页面（组件）

# License
MIT
