##
1. ��װSPATemplate

``` bash
dotnet new --install Microsoft.AspNetCore.SpaTemplates::*
```

2. ����һ��ʹ�� Angular ��SPA���ּ�

```bash
dotnet new angular
```

3. ��װ PrimeNG

```bash 
npm install primeng --save
npm install font-awesome --save
```

4. �޸�webpack�ļ�
�� webpack.config.vendor.js �ļ������
```js
    'font-awesome/css/font-awesome.css',
    'primeng/primeng',
    'primeng/resources/themes/omega/theme.css',
    'primeng/resources/primeng.min.css', 
```

����� gif ��rules��
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

5. �޸� Home\Index.cshtml �ļ�
Ŀǰ�� PrimeNg ��δ֧�� pre-rendering ������ ����޸� ..\Views\Home\Index.cshtl
```html
<app asp-prerender-module="ClientApp/dist/main-server">Loading...</app>
```
Ϊ
``` html
<app>Loading...</app>
```

6. ����Webpack
ÿ���޸�webpack�ļ������ֹ��������������������

```bash
webpack --config webpack.config.vendor.js
```

## �ο���Դ
1. [Upgrading JavaScriptServices and PrimeNG From Angular 2 to Angular 4+](http://lightswitchhelpwebsite.com/Blog/tabid/61/EntryId/4306/Upgrading-JavaScriptServices-and-PrimeNG-From-Angular-2-to-Angular-4.aspx)
2. 