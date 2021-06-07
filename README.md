# LearningReact
This repo is for learn React.



一、标题写法：
第一种方法：
1、在文本下面加上 等于号 = ，那么上方的文本就变成了大标题。等于号的个数无限制，但一定要大于0个哦。。
2、在文本下面加上 下划线 - ，那么上方的文本就变成了中标题，同样的 下划线个数无限制。
3、要想输入=号，上面有文本而不让其转化为大标题，则需要在两者之间加一个空行。
另一种方法：（推荐这种方法；注意⚠️中间需要有一个空格）
关于标题还有等级表示法，分为六个等级，显示的文本大小依次减小。不同等级之间是以井号  #  的个数来标识的。一级标题有一个 #，二级标题有两个# ，以此类推。
例如：
# 一级标题  
## 二级标题  
### 三级标题  
#### 四级标题  
##### 五级标题  
###### 六级标题 
二、编辑基本语法  
1、字体格式强调
 我们可以使用下面的方式给我们的文本添加强调的效果
*强调*  (示例：斜体)  
 _强调_  (示例：斜体)  
**加重强调**  (示例：粗体)  
 __加重强调__ (示例：粗体)  
***特别强调*** (示例：粗斜体)  
___特别强调___  (示例：粗斜体)  
2、代码  
`<hello world>`  
3、代码块高亮  
```
@Override
protected void onDestroy() {
    EventBus.getDefault().unregister(this);
    super.onDestroy();
}
```  
4、表格 （建议在表格前空一行，否则可能影响表格无法显示）
 
 表头  | 表头  | 表头
 ---- | ----- | ------  
 单元格内容  | 单元格内容 | 单元格内容 
 单元格内容  | 单元格内容 | 单元格内容  
 
5、其他引用
图片  
![图片名称](https://www.baidu.com/img/bd_logo1.png)  
链接  
[链接名称](https://www.baidu.com/)    
6、列表 
1. 项目1  
2. 项目2  
3. 项目3  
   * 项目1 （一个*号会显示为一个黑点，注意⚠️有空格，否则直接显示为*项目1） 
   * 项目2   
 
7、换行（建议直接在前一行后面补两个空格）
直接回车不能换行，  
可以在上一行文本后面补两个空格，  
这样下一行的文本就换行了。
或者就是在两行文本直接加一个空行。
也能实现换行效果，不过这个行间距有点大。  
 
8、引用
> 第一行引用文字  
> 第二行引用文字


# Walden 最适合东半球同学使用的文档框架

[![Build Status](https://travis-ci.org/meolu/walden.svg?branch=master)](https://travis-ci.org/meolu/walden)

或许是极人性化的一个文档管理框架，最适合部署在内网作为内网文档管理，url即目录层级。markdown+git+web搭配，让你一下子就喜欢上写文档分享。一分钟上手，有兴趣可挖掘隐藏技巧。

[官网主页](http://www.huamanshu.com/walden.html) | [体验Demo](http://walden.huamanshu.com/) | 案例-[瓦力-walle](http://doc.huamanshu.com/瓦力/)

## 演示
![walden](https://raw.github.com/meolu/Walden/master/static/screenshots/walden.gif)


## 特点

* Markdown语法
* 修改后实时展现，无编译
* 多模板支持
* 图片、附件上传，自动生成url
* 多项目
* 任意定义目录嵌套、定义文档，目录与文档均可中文（甚至推荐中文）
* 文档、图片、附件同步保存至git，这下你安心了吧

## 一、安装

零安装、零配置，无数据库，不需要composer，开箱即用。只需要你有一台安装了git命令行，php5.3，nginx环境的linux机器。

## 二、快速开始

```php
vi Config.php
return [
    // 项目留空保存文档和附件的git地址，可以是在github，好吧，不想公开，可以bitbucket。

    // 1.php进程的用户的id_rsa.pub已添加到git的ssh-key。这样才可以推送markdown下的文件。
    'git' => 'git@github.com:meolu/Walden-markdown-demo.git',

    // 2.好吧，如果实在不想加key，可以直接明文用户名密码认证的http(s)地址也可以。
    // 'git' => 'https://username:password@github.com/meolu/Walden-markdown-demo.git',
];
```

## 三、nginx简单配置

```
server {
    listen       80;
    server_name  Walden.dev;
    root /the/dir/of/Walden;
    index index.php;

    # 建议放内网做文档服务
    #allow 192.168.0.0/24;
    #deny all;

    location / {
        try_files $uri $uri/ /index.php$is_args$args;
    }

    location ~ \.php$ {
        try_files $uri =404;
        fastcgi_pass   127.0.0.1:9000;
        fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
        include        fastcgi_params;
    }
}
```


## 自定义模板

前端同学可以自己定义模板，在templates下新建一个模板目录，包含预览模板：`markdown-detail-view.php`，编辑模板：`markdown-editor-view.php`，然后修改`Config.php`的`template`为你的模板项目。

最后，当然希望你可以给此项目提个pull request，目前只有一个bootstrap的默认模板：(


## to do list

* 文档搜索
* 文档删除，重命名UI化


## CHANGELOG
瓦尔登的版本记录：[CHANGELOG](https://github.com/meolu/walden/blob/master/CHANGELOG.md)




