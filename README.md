# jump
微信跳一跳复刻 CocosCreator + Typescript 在线试玩 https://potato47.github.io/game/jump/

# 简单讲两句

熬了两天夜写的，没想到后来有人找我拿这个做外包，还有别人做外包找我做顾问的。。。还有cocos的公众号拿去发文章的，还有腾讯课堂的老师拿去讲课的，当然，都没跟我打招呼。

说一下核心逻辑

一开始我做的时候想用物理引擎，或者简单的用一下碰撞组件，后来发现很麻烦，不好控制落点

多次观察微信跳一跳的界面发现了一个规律：

人物每次跳跃落地都是固定的几个点，如果把跳跃的方块看做九宫格的正方形，那么落点一共可以分为五个，也就是上下左右中

一个非常简便的方法就出来了：

不需要人物落地之后再判断是否跳到方块上

人物跳跃之前就根据跳跃距离（跳跃距离根据蓄力时间得出），算出人物跳跃后距离目标方块哪个点（上下左右中）最近，直接让人物执行一个固定距离的跳跃动作就可以了，完全不需要物理引擎和碰撞系统，每个落点都是预设好的

当然要设定一个差值，当大于这个差值时，就代表跳到了方块外面

---

我还写了一个2d横版的跳一跳，感兴趣的可以看我另一个小游戏集合项目 https://github.com/potato47/so-many-games
