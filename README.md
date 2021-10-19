# web 字体压缩示例 - fontSpider

> 使用 [font-spider](https://github.com/aui/font-spider) 库来作压缩处理。  
> 使用 [tesla font](https://www.dafont.com/tesla.font) 作为示例字体。

## 下载字体

链接： [tesla font](https://www.dafont.com/tesla.font)

## 安装 font-spider

```sh
npm install font-spider
```

## 使用

1. 添加 css 文件

   ```css
   @font-face {
     font-family: 'source';
     src: url('../font/source.eot');
     src: url('../font/source.eot?#font-spider') format('embedded-opentype'), url('../font/source.woff2')
         format('woff2'), url('../font/source.woff') format('woff'), url('../font/source.ttf')
         format('truetype'), url('../font/source.svg') format('svg');
     font-weight: normal;
     font-style: normal;
   }
   ```

   - 将 font-family 名字改成自己想使用的名字
   - 将该段 css 代码中所有 `../font/source.*` 文件替换为 `tesla font` 的 `ttf` 文件所在路径，后缀名不需要改变。

   > 必须保证 `ttf` 文件存在，`font-spider` 会自动生成相应的其他文件。

2. 在 `html` 文件中引入该 `css` 文件，并为需要引用该字体的元素添加 `font-family` 的样式

   ```html
   <!-- index.html 作为示例 -->
   <head>
     <link rel="stylesheet" href="./css/tesla-font.css" />
     <style>
       .container {
         font-family: 'tesla font';
       }
     </style>
   </head>
   <body>
     <div class="container"></div>
   </body>
   ```

3. 运行命令压缩字体

   ```sh
   # npx font-spider [options] <htmlfile ...>
   npx font-spider index.html
   ```

## 其他

更多使用方法和限制参考 [font-spider 文档](https://github.com/aui/font-spider)。
