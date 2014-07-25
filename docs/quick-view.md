#视图
###1、概念
视图即MVC里面的V，View的缩写。视图是数据的表现层，视图的数据主要由控制器赋予。

###2、视图文件
视图文件保存于目录`HianoApp/View/[模块]/[控制器]/`里，每个视图文件对应控制器里的一个动作，文件名命名规则为`xxx.tpl`,xxx为视图对应的动作的名称。

###3、视图的语法

视图的文件语法由项目使用的视图引擎决定，默认的是拓展的Smarty模板引擎 - [Smarty4hiano](https://github.com/kasonyang/smarty4hiano/)。

视图文件示例

HianoApp/View/Home/Index/index.tpl

    <html>
        <body>
            {{* 输出content变量 *}}
            {{$content}}
        </body>
    </html>


