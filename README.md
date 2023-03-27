# 2023_test

2023/3/13 创建，用于学习


########## ########## ########## ########## ########## ########## ########## ##########

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


########## ########## ########## ########## ########## ########## ########## ##########

【Vue】


********** ********** 2023.03.26 ********** **********

    (t) => t !== todo
    
    //实际上就是
    
    function(t){
        return t !==todo
    }

********** ********** ********** ********** **********


########## ########## ########## ########## ########## ########## ########## ##########

【Webpack】


********** ********** 2023.03.27 ********** **********

    //webpack5 中引入图片
    
     {
        test:/\.(jpg|png|gif)$/,
        type:"asset",
        //解析
        parser: {
          //转base64的条件
          dataUrlCondition: {
            maxSize: 25 * 1024, // 25kb
          }
        },
        generator:{ 
          //与output.assetModuleFilename是相同的,这个写法引入的时候也会添加好这个路径
          filename:'img/[name].[hash:6][ext]',
          //打包后对资源的引入，文件命名已经有/img了
          publicPath:'./'
        },
      },


********** ********** 2023.03.27 ********** **********

    //webpack5 中映射文件
    //修改 webpack.config.js
    
    module.exports = {
        ...
        devtool: 'source-map'
    }
    
    sourcemap配置的值有： [inline-|hidden-|eval-][nosources-][cheap-[module-]] [source-map]

    // eval： 使用eval包裹模块代码, 在尾部用拼接注释 //# sourceURL=webpack-internal:///./src/index.js，不会生成map文件
    // source-map： 产生.map文件
    // cheap： 不包含列信息，也不包含loader的sourcemap
    // module： 包含loader的sourcemap（比如jsx to js ，babel的sourcemap）
    // inline： 将.map作为DataURI嵌入，不单独生成.map文件（这个配置项比较少见）
    // nosources: 隐藏源代码，源代码的文件名
    // hidden: 隐藏源代码,提示编译后的文件名

    // 开发环境要考虑：速度快，调试友好
    // 速度： eval > inline > cheap
    // 调试: source-map > cheap-module-source-map > cheap-source-map
    // 推荐： eval-source-map/eval-cheap-module-source-map

    // 生产环境，要考虑： 源码要不要隐藏，调试要不要友好
    // inline和eval会把map放进js，所以生成环境不要使用行内
    // 代码有隐藏要求： hidden-source-map / nosources-source-map
    //推荐： nosources-cheap-source-map/hidden-cheap-source-map
    
    
********** ********** ********** ********** **********
