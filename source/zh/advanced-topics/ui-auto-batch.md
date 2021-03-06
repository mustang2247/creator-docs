# BMFont 与 UI 合图自动批处理

## 前言

**本篇文档基于 Cocos Creator v1.4.0 完成**

UI 界面里面经常会使用一些 Label 组件来进行描述性的说明，而这些 Label 组件会打断引擎本身的自动批处理功能，导致 UI 界面的 Draw Call 非常的高。
由于 BMFont 和艺术数字也是使用图片进行渲染，所以我们在 1.4 版本添加了 BMFont 和艺术数字与其它 UI 图片进行合图渲染的功能。

使用这个功能非常的简单，你只需要参考 [自动图集资源](../asset-workflow/auto-atlas.html) 新建一个自动图集资源配置，然后把所有你希望进行合图的 UI 图片，
BMFont 和艺术数字都拖到自动图集资源所在的目录即可。如果你希望最后 UI 的 Draw call 数量尽可能低，你需要保证合图的数量尽可能的少。最好是使用一张合图就可以
容纳所有的 UI 元素，这样理论上，如果你不使用系统字体和 TTF 字体，你的 UI 界面的 Draw call 数量可以达到 1。



## 注意事项
1. 由于 creator 的合图功能是在项目导出的时候进行的，所以需要对发布的项目进行合图批次渲染功能测试。
2. 在导入 BMFont 的资源的时候，需要把 .fnt 和相应的 png 图片放在同一个目录下面。
3. LabelAtlas 底层渲染采用的跟 BMFont 一样的机制，所以也可以和 BMFont 及其它 UI 元素一起合图来实现批次渲染。
