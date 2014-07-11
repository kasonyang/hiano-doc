##开始使用Hiano
>开始前，请先安装[composer](https://getcomposer.org/)
###创建你的第一个App
在命令行下，执行下面的这条命令

    >composer create-project kasonyang/hiano-app

composer将会在当前目录下初始化一个新的工程，目录名为`hiano-app`。

工程目录结构如下：

    /hiano-app
        HianoApp
            Config                          #配置目录
                hitar.config.php               --hitar配置文件
                system.config.php              --系统配置文件
            Controller                      #控制器目录
                Home
                    IndexController.php        --控制器示例
                    main.php                   --模块入口文件，通常用于注册过滤器
            Filter                          #过滤器目录
                HomeFilter.php                 --过滤器示例
            Model                           #模型目录
                User.php                       
            View                            #视图模板目录
                Home
                    Index
                        index.tpl              --模板文件
                master.master                  --父模板文件
        vender                              #vender目录
            ...
        www                                 #公开文件目录
            ...


