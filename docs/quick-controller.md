#控制器
###1、概念
控制器即MVC里面的C，Controller的缩写。控制器主要要用于从模型读取数据、处理用户的输入、向视图传递数据。

###2、控制器文件
控制器文件保存于目录`HianoApp/Controller/模块/`里，文件名命名规则为`XxxController.php`,Xxx为控制器的名称，每个控制器文件必须包含一个和文件同名的控制器类。

###3、控制器类

每一个控制器都是一个类，命名规则为`XxxController`,控制器类的基类必须为`\Hiano\Controller\Controller`或其派生类。

控制器包含一个以上的动作。

###4、动作

动作为控制器里的一个方法，必须为public类型的方法，命名规则为`xxxAction`，xxx为动作名。

>动作可以为空，即什么也不做，但是动作对应的视图还是会显示！

###5、动作的返回值

动作的返回值类型可以为以下几种

* null 或 无返回值

    视图正常显示

* FALSE

    不显示视图

* string

    不显示视图，返回值已字符串形式返回给浏览器


控制器类示例

HianoApp/Controller/Home/IndexController.php

    <?php
    namespace HianoApp\Controller\Home;
    //index控制器
    class IndexController extends \Hiano\Controller\Controller{
        //index动作
        function indexAction(){
            //什么都不做，视图会显示
        }
        function demoAction(){
            return false;//返回false，视图则不显示
        }
        function helloAction(){
            return 'hello';//输出"hello",不显示视图
        }
    }

