# Yoman 使用教程

1.在官网下载最新nodejs，安装后node的版本和npm的版本才能达到Yoman要求的最低标准。
2.进入yoman官网按照开始步骤来：
（1）
npm install -g yo bower grunt-cli gulp
（2）
npm install -g generator-webapp
（3）
mkdir my-yo-project $ cd my-yo-project
and then run:

yo webapp
这时候会报出一个错误，官方文档上没有给出解决方案，错误如下：
priusdeMacBook-Pro:my-yo-project prius$ yo webapp
module.js:338
    throw err;
          ^
Error: Cannot find module 'underscore.string'
    at Function.Module._resolveFilename (module.js:336:15)
    at Function.Module._load (module.js:278:25)
    at Module.require (module.js:365:17)
    at require (module.js:384:17)
    at Object.<anonymous> (/usr/local/lib/node_modules/generator-webapp/app/index.js:8:10)
    at Module._compile (module.js:460:26)
    at Object.Module._extensions..js (module.js:478:10)
    at Module.load (module.js:355:32)
    at Function.Module._load (module.js:310:12)
    at Module.require (module.js:365:17)
    at require (module.js:384:17)
（略微蛋疼）
3. 于是google找到一个解决办法是：
cd /usr/local/lib/node_modules/generator-webapp/
npm install underscore.string
其实就是generator-webapp下面缺少underscore.string的包，npm install一下就好了。

4. 重新输入yo webapp就会出现下面成功的提示：
priusdeMacBook-Pro:my-yo-project prius$ yo webapp

     _-----_
    |       |    .--------------------------.
    |--(o)--|    |  'Allo 'allo! Out of the |
   `---------´   |    box I include HTML5   |
    ( _´U`_ )    | Boilerplate, jQuery, and |
    /___A___\    |   a Gruntfile to build   |
     |  ~  |     |         your app.        |
   __'.___.'__   '--------------------------'
 ´   `  |° ´ Y `

? What more would you like?
❯◉ Sass
 ◉ Bootstrap
 ◉ Modernizr

5.如果顺利安装上bower，倒还好说直接grunt server就可以了，直接自动打开首页，
如果bower下载不下来，那只能grunt server --force，一样也能启动服务，只不过bower安装的那些前端包文件缺失。

