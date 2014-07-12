##开始使用Hiano
>开始前，请先安装[composer](https://getcomposer.org/)
###创建你的第一个App
在命令行下，执行下面的这条命令

    >composer create-project kasonyang/hiano-app

composer将会在当前目录下初始化一个新的工程，目录名为`hiano-app`。

工程目录结构如下：

    /hiano-app
        /HianoApp
            /Config                          #配置目录
                hitar.config.php               --hitar配置文件
                system.config.php              --系统配置文件
            /Controller                      #控制器目录
                /Home
                    IndexController.php        --控制器示例
                    main.php                   --模块入口文件，通常用于注册过滤器
            /Filter                          #过滤器目录
                HomeFilter.php                 --过滤器示例
            /Model                           #模型目录
                User.php                       
            /View                            #视图模板目录
                /Home
                    /Index
                        index.tpl              --模板文件
                master.master                  --父模板文件
        /vender                              #vender目录
            ...
        /www                                 #公开文件目录
            ...

###让你的App跑起来
####Nginx的配置方法
将如下配置添加到Nginx的配置文件里，注意填写`hiano/www`的完整路径

    location / {
        root path/to/hiano-app/www;#请填写hiano/www的完整路径
        if (!-f $request_filename){
            rewrite (.*) /index.php;
        }
    }
    location ~ \.php$ {
        root           path/to/hiano-app/www;#请填写hiano/www的完整路径
        fastcgi_pass   127.0.0.1:3000;
        fastcgi_index  index.php;
        fastcgi_param  SCRIPT_FILENAME $document_root/$fastcgi_script_name;
        include        fastcgi_params;
    }

####Apache的配置方法
请确保您的Apache支持.htaccess文件配置且已开启mod_rewrite模块

将目录`hiano-app\www`的完整路径设置为Apache的DocumentRoot，并为该目录设置相应的权限即可，具体设置方法请查看Apache的官方文档。

    