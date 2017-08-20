# Intro
分析用户行为轨迹数据，并将分析的数据生成json文件。

# Motivation
我做这个项目的原因是，希望可以做一个”自产自销“的一个app。 如何理解“自产自销”呢？大概的原理可以用下图来描述：
![self consume](https://www.draw.io/?lightbox=1&highlight=0000ff&edit=_blank&layers=1&nav=1&title=locusxml#Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fazl397985856%2Flocus%2Fmaster%2Flocusxml)

用户在使用我的app 的时候，我会收集用户的数据信息，然后将数据信息上报，然后集中处理（locus处理），生成一个json 文件，该文件又可以被app
直接消费。 消费的结果是什么呢？   就是app 可以针对用户的操作习惯做一些优化处理，最典型的就是资源预加载。
因此我打算在第一版本先做这个功能，后续可能会加入智能推送等业务。
我的目标是，app 可以不用自己处理类似这样的数据和逻辑，就可以享受到更加的用户体验（智能预加载等）

# License
MIT
