##
1. 安装SPATemplate

``` bash
dotnet new --install Microsoft.AspNetCore.SpaTemplates::*
```

2. 创建一个使用 Angular 的SPA脚手架

```bash
dotnet new angular
```

3. 安装 PrimeNG

```bash 
npm install primeng --save
npm install font-awesome --save
```

4. 修改webpack文件
打开 webpack.config.vendor.js 文件，添加
```js
    'font-awesome/css/font-awesome.css',
    'primeng/primeng',
    'primeng/resources/themes/omega/theme.css',
    'primeng/resources/primeng.min.css', 
```

并添加 gif 到rules中
```js
const sharedConfig = {
        stats: { modules: false },
        resolve: { extensions: [ '.js' ] },
        module: {
            rules: [
                { test: /\.(png|gif|woff|woff2|eot|ttf|svg)(\?|$)/, use: 'url-loader?limit=100000' }
            ]
        },
```

5. 修改 Home\Index.cshtml 文件
目前， PrimeNg 尚未支持 pre-rendering 技术， 因此修改 ..\Views\Home\Index.cshtl
```html
<app asp-prerender-module="ClientApp/dist/main-server">Loading...</app>
```
为
``` html
<app>Loading...</app>
```

6. 运行Webpack
每次修改webpack文件后，需手工运行命令进行重新配置

```bash
webpack --config webpack.config.vendor.js
```

## 参考资源
1. [Upgrading JavaScriptServices and PrimeNG From Angular 2 to Angular 4+](http://lightswitchhelpwebsite.com/Blog/tabid/61/EntryId/4306/Upgrading-JavaScriptServices-and-PrimeNG-From-Angular-2-to-Angular-4.aspx)
2. 