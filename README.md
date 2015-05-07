# fis-parser-handlebars

A parser plugin for fis to precompile handlebars template.

### 1. 安装插件：

> npm install -g fis-parser-handlebars

### 2. 配置

```js
// fis-conf.js
fis.config.set('modules.parser.handlebars', 'handlebars');
fis.config.set('project.fileType.text', 'handlebars');
fis.config.set('roadmap.ext.handlebars', 'js');
```

foo.handlebars的模板文件，其中的内容是：
```hanblebars
<div class="entry">
  <h1>{{title}}</h1>
  <div class="body">
    {{body}}
  </div>
</div>
```

然后你再写一个叫foo.js的js文件，内容是：

```js
var tpl = __inline('foo.handlebars');
var context = {title: "My New Post", body: "This is my first post!"};
var html = console.log(tpl(context));
console.log(html);
```

记得在页面上使用handlebars的 [runtime版本](http://builds.handlebarsjs.com.s3.amazonaws.com/handlebars.runtime-v3.0.3.js) 作为运行时框架。
