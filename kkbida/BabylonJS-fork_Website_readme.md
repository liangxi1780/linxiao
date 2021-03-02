# Babylon.js website

## Installation process

``` sh
    npm install -g gulp
    npm install
```

## Development mode

Web site will be available at http://localhost:8080/

``` sh
    gulp run
```

## Additional options for the page

### Page title

this property available as part of page level Json property

``` sh
    "title": "BabylonJS - 3D engine based on WebGL/Web Audio and JavaScript"
```

### Meta tags

meta tags can be unique for each page. This property available as part of page level Json property and contains list of tags

``` json
    "metaTags": [
    {
      "name": "description",
      "content": "BabylonJS - 3D engine based on WebGL/Web Audio and JavaScript"
    },
    {
      "property": "og:title", //optional property for open graph
      "content": "BabylonJS - 3D engine based on WebGL/Web Audio and JavaScript"
    }
  ]
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)