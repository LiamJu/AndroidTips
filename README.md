# AndroidTips
一些安卓开发技巧

## 快速查找安卓系统资源
以查找TextView的默认style为例
1. 打开TextView.java
2. 找到两个参数的构造方法
3. 看到com.android.internal.R.attr.textViewStyle，找到系统的attrs.xml文件
4. 打开保存在本地的sdk路径
5. 打开platforms，打开你想查看的安卓版本，以`android-24为例`
6. 打开路径`data/res/values/attrs.xml`，就可以找到`textViewStyle`属性了,接着查找`textViewStyle`对应的具体属性
7. 找到`textViewStyle`后应该找具体的主题`themes.xml`，然后去找`textViewStyle`对应的`styles.xml`，所以接下来找`themes.xml`
8. android-24提供了多套主题，其中`themes_holo.xml`等主要就是为了向上兼容。
9. 这里以`themes-material.xml`为例，查找`textViewStyle`，同样可以找到多个`textViewStyle`，以`Widget.Material.TextView`为例
10. 打开`style_material.xml`，查找`Widget.Material.TextView`，发现它继承了`Widget.TextView`，发现这个Style文件里并没有`Widget.TextView`，再到`styles.xml`中找
11. 这个时候，经过了这么多步骤，终于找到了TextView默认的具体属性
