在公司里边，随着公司业务的增长，一个项目的功能也会随着递增式的增长，代码也会越来越多。如果不加以拆分，势必会造成维护困难，一个bug会随之引发一系列血案.....。还有，也许会有一天，老板会突发奇想 要把项目中的某部分功能单独抽出来，做成一个单独的app，此时copy一份？此时大量的重复代码 维护成本倍增。

##### Xcode中的**Workspace**

Workspace是一种xcode文件，用于分组projects和其他文件，便于我们使用它们，一个workspace可以包含多个project和其他你想要引入的文件，除了组织各种project外，workspace还可以管理各个target之间的依赖关系。Xcode中创建一个Workspace：

第一：File-&gt;New-&gt;Workspace

![](/assets/Snip20180920_7.png)![](/assets/Snip20180920_6.png)

第二：给该workspace起一个名字

![](/assets/屏幕快照 2018-09-20 下午2.46.50.png)

创建成功后的界面如下：

![](/assets/屏幕快照 2018-09-20 下午2.47.41.png)

创建完成后我们便可以将项目中各个业务模块相互分离，如：分成一个Main, Base,Login.\(根据自己项目的实际情况进行拆分\)

此时我们分别在workspzce中创建对应的模块（在此我的Base.Login,Test都是Framework）

![](/assets/屏幕快照 2018-09-20 下午3.33.56.png)

创建完成后点击以.xcworkspace的文件打开工程 然后将刚才创建的几个项目依次添加到工程中去

![](/assets/Snip20180920_7.png)         ![](/assets/Snip20180920_8.png)

添加完成后：

![](/assets/Snip20180920_13.png)

此时如果Main中需要调用base中的某个方法在（此注意如果base中的某个方法是被外界调用的一定要声明为public）

![](/assets/Snip20180920_14.png)

在Main中添加base的依赖

![](/assets/Snip20180920_11.png)

然后在需要调用base方法的某个地方引入相应库

![](/assets/Snip20180920_15.png)

