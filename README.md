# 2023_test

2023/3/13 创建，用于学习


########## ########## ########## ########## ########## ########## ########## ########## ########## ##########

【MySQL】


********** ********** 2023.03.16 ********** ********** 

    mysql -u root -p    //连接到 MySQL 服务器

    source 文件地址    //使用source命令将数据上传到MySQL服务器

    show databases;     //查看目录结构实现数据库
    
    use 数据库名称;    //切换到数据库


********** ********** 2023.03.16 ********** **********

    //中文乱码，修改my.ini文件：

    [client]
    default-character-set=utf8

    [mysql]
    default-character-set=utf8

    [mysqld]
    init_connect='SET collation_connection = utf8_unicode_ci'
    init_connect='SET NAMES utf8'
    character-set-server=utf8
    collation-server=utf8_unicode_ci skip-character-set-client-handshake

    //重启mysql服务，mysql里面用 show variables like 'char%'; 可以看有没有配置好，除了file_system全是utf8说明搞定


********** ********** ********** ********** **********


########## ########## ########## ########## ########## ########## ########## ########## ########## ##########

【Vue】


********** ********** 2023.03.26 ********** **********

    (t) => t !== todo
    
    //实际上就是
    
    function(t){
        return t !==todo
    }

********** ********** ********** ********** **********
