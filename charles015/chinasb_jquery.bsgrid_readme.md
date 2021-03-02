jQuery.bsgrid 简单易用的jQuery Grid插件
=======================================

 jquery bsgrid ，A simple jQuery Grid plugin with pagation, export and easy to expand. 一个简单易用的jQuery Grid插件，支持分页或不分页，支持json、xml数据格式，对导出友好，扩展性友好。

本插件的早期及当前版本已在多个项目中使用。

开源协议：Apache Licence 2
 
插件版本：1.21
 
更新日期：2014-10-16
 
在线演示：[http://bsgrid.oschina.mopaas.com/](http://bsgrid.oschina.mopaas.com/)
 
详细介绍：[http://thebestofyouth.com/project/jquery_bsgrid.html](http://thebestofyouth.com/project/jquery_bsgrid.html)
 
Git@OSC托管的图片可能不稳定(会造成下面部分图片显示不出)，可直接右键另存 README.md.pdf 到本地查看此文档说明。

#####首先给出典型效果图示#####
1，内置多套皮肤（点击下面对应皮肤图片可查看示例页面），并可非常容易的自定义皮肤（参考 Custom Blue Style ）
 
 
 
 
 
 
 
 
 
	 
		 ExtJS Gray Style
             
             
              
         
		 ExtJS Blue Style
             
             
              
         
     
     
		 ExtJS Access Style
             
             
              
         
		 FlexiGrid Gray Style
             
             
              
         
     
     
		 Dhtmlx Sky Blue Style
             
             
              
         
		 Custom Blue Style
             
             
              
         
     
 
 
2，可以非常方便的集成第三方分页工具条使用（点击下面对应皮肤图片可查看示例页面）
 
 
	 
		 With jqPagination
             
             
              
         
		 With jquery_pagination
             
             
              
         
     
     
		 With jPaginate
             
             
              
         
		 With jPages
             
             
              
         
     
     
		 With smartpaginator
             
             
              
         
		 With jPaginator
             
             
              
         
     
 
 


###bsgrid的由来###
&emsp;&emsp;首先，澄清插件名称为何叫bsgrid，是因为敝人常用bs开头的字符做英文账号的缘故。bsgrid诞生的原因是主流插件或框架的grid使用或扩展比较复杂。
 
以下仅简单说下各插件或框架的grid：
 &emsp;&emsp;1，目前主流Grid基本比较适用于内部系统，对于外部系统适用而言，想要改变皮肤样式，字体大小等都非常困难；
 &emsp;&emsp;2，主流Grid封装的太好，这反而造成了其扩展性能不是很好，并且其methods、properties很多，上手不容易；
 &emsp;&emsp;3，主流grid大多数不提供无分页情况下后台数据的全部展现。

###bsgrid的特点###
&emsp;&emsp;1，轻量级，基于jQuery及HTML Table，除了对加载数据、分页、渲染数据的简单封装外，不额外增加特别的功能；模块化JS代码，可按需加载；CSS样式精致简洁，对于扩展修改非常容易；
 &emsp;&emsp;2，使用友好，对于一个简单的表格展现，仅仅数十行代码即可完成，并且支持json、xml两种数据格式；且支持友好的导出参数构建；
 &emsp;&emsp;3，内置多套经典样式风格，效果参看examples\grid\themes\\*.html；可非常容易的修改表格使用字体大小，参看示例examples\grid\themes\custom.html，仅需修改该示例样式中的两处font-size即可；
 &emsp;&emsp;4，自带load加载数据遮罩，并很容易进行扩展或重写；
 &emsp;&emsp;5，扩展性好，插件有特别好的扩展性，易于对插件本身进行局部甚至较大的修改，易于改变展现样式、渲染数据；插件放开了属性及方法的全局修改权限，所有方法都可在外部进行全局重写，而无需修改插件本身的代码。

###对于主流Grid的简单理解###
大概说下目前的一些主流grid插件或框架的grid
 &emsp;&emsp;1，ExtJS，功能丰富，封装好，但属重量级产品，需要加载大体积文件，且响应速度较慢，需商业授权，一般用于内部系统；
 &emsp;&emsp;2，DHtmlx，同样功能丰富，封装好，不过其可以根据所需要的模块进行加载，速度方面快于ExtJS，需商业授权，由于其样式不易修改，同样一般用于内部系统；
 &emsp;&emsp;3，EasyUI，基于jQuery，语法使用jQuery，却部分地方像ExtJS的写法，在不需其源码的情况下无需商业授权，因无源码而不方便按需模块化加载，也很难改变皮肤样式；
 &emsp;&emsp;4，jQGrid，基于jQuery，开源免费且功能特别强大，但同样其样式不易修改；
 &emsp;&emsp;5，Flexigrid，基于jQuery，功能逊色，但轻量级，methods、properties较少，不失为想用ExtJS Grid或EasyUI Grid却难以上手这两者的另外一个选择。

###bsgrid示例目录###
 
以下列出Grid及Grid With ArtDialog的示例并作以说明；Util、Button、Form、Paging、Grid With Other Pagination部分的示例简述如下：

Util：  演示util.min.js，提供form表单序列化为字符串的方法(区别于jquery的param方法)，以及form表单序列化name为字符串的方法
Button：演示icon.min.css，提供两种图标样式
Form：  演示form.min.js、form.min.css，对于表单的敏捷处理，包括获取表单值、给表单赋值、表单的查看新增编辑模式、表单各种模式下的tip提示
Paging：演示grid.paging.min.js分页工具条，不依赖grid.min.js
Grid With Other Pagination：演示Grid集成第三方分页工具条使用
Merged Files: 目录builds/merged，合并经常一起使用的css、js，合并文件描述文件builds/readme
              grid.simple.min.css     合并grid、paging分页css样式
              grid.simple.min.js      合并grid、paging分页js脚本
              grid.all.min.css        合并grid、paging分页、icon图标css样式
              grid.all.min.js         合并grid、paging分页、grid导出构建js脚本
              bsgrid.all.min.css      合并grid、paging分页、icon图标、form表单css样式
              bsgrid.all.min.js       合并grid、paging分页、grid导出构建、form表单js脚本

1， Example Index 
2， Simple Grid 
3， Simple zh-CN Grid 
4， Simple XML Data Grid 
5， No Pagation 
6， No Diaplay Blank Rows 
7， No Data 
8， Grid With Checkbox 
9， Grid With Little Paging 
10， Standard Grid 
11， Multi Grid 
12， Export Grid 
13， Grid with ArtDialog 
14， Grid And Form with ArtDialog 
 
 

#####1， Example Index #####
![Example Index](http://git.oschina.net/bs2004/jquery.bsgrid/raw/master/WebContent/documention/images/jquery.bsgrid-01_examples_index.png)

#####2， Simple Grid #####
![Simple Grid](http://git.oschina.net/bs2004/jquery.bsgrid/raw/master/WebContent/documention/images/jquery.bsgrid-02_simple_grid.png)
 
引用文件：
    &lt;link rel="stylesheet" href="../../builds/merged/grid.simple.min.css"/&gt;
    &lt;script type="text/javascript" src="../../plugins/jquery-1.4.4.min.js"&gt;&lt;/script&gt;
    &lt;script type="text/javascript" src="../../builds/js/lang/grid.en.min.js"&gt;&lt;/script&gt;
    &lt;script type="text/javascript" src="../../builds/merged/grid.simple.min.js"&gt;&lt;/script&gt;
实现代码：
    &lt;table id="searchTable" class="bsgrid"&gt;
        &lt;tr&gt;
            &lt;th w_index="XH" width="5%;"&gt;XH&lt;/th&gt;
            &lt;th w_index="ID" width="5%;"&gt;ID&lt;/th&gt;
            &lt;th w_index="CHAR" w_align="left" w_tip="true" width="15%;"&gt;CHAR&lt;/th&gt;
            &lt;th w_index="TEXT" w_align="left" w_length="50" width="30%;"&gt;TEXT&lt;/th&gt;
            &lt;th w_index="DATE" width="15%;"&gt;DATE&lt;/th&gt;
            &lt;th w_index="TIME" width="15%;"&gt;TIME&lt;/th&gt;
            &lt;th w_index="NUM" width="5%;"&gt;NUM&lt;/th&gt;
            &lt;th w_render="operate" width="10%;"&gt;Operate&lt;/th&gt;
        &lt;/tr&gt;
    &lt;/table&gt;
    &lt;script type="text/javascript"&gt;
        $(function () {
            $.fn.bsgrid.init('searchTable', {
                url: 'data/simple.json',
                // autoLoad: false,
                pageSizeSelect: true,
                pageSize: 10
            });
        });
    
        function operate(record, rowIndex, colIndex, options) {
            return '&lt;a href="#" onclick="alert(\'ID=' + record['ID'] + '\');"&gt;Operate&lt;/a&gt;';
        }
    &lt;/script&gt;
 

#####3， Simple zh-CN Grid #####
![Simple zh-CN Grid](http://git.oschina.net/bs2004/jquery.bsgrid/raw/master/WebContent/documention/images/jquery.bsgrid-03_simple_zh-CN_grid.png)
 
1，插件语言本地化文件：grid.en.min.js、grid.zh-CN.min.js、grid.zh-TW.min.js

2，行间隔色配置：stripeRows: true

3，行hover样式：添加如下样式
   /* row hover */
   .bsgrid tr:hover {
        background-color: #ffe48d;
   }
 

#####4， Simple XML Data Grid #####
![Simple XML Data Grid](http://git.oschina.net/bs2004/jquery.bsgrid/raw/master/WebContent/documention/images/jquery.bsgrid-04_simple_XML_data_grid.png)
 
默认的是json格式，换加载XML格式数据：
方式1，全局修改加载数据格式：
　　$.fn.bsgrid.defaults.dataType = 'xml';
方式2，单grid修改加载数据格式：
　　$.fn.bsgrid.init('searchTable', {
            url: 'data/simple.xml',
            dataType: 'xml',
            pageSizeSelect: true,
            pageSize: 10
　　});
 

#####5， No Pagation #####
支持展示后台的全部数据，分页工具条变为如下只显示总数的样式：
 
![No Pagation](http://git.oschina.net/bs2004/jquery.bsgrid/raw/master/WebContent/documention/images/jquery.bsgrid-05_no_pagation.png)
 
实现代码：将pageAll设置为true即可，后台数据格式与分页后台数据格式一致
   $.fn.bsgrid.init('searchTable', {
       url: 'data/simple.json',
       pageAll: true
   });
补充说明：不分页则无需加载grid.paging.min.css、grid.paging.min.js
 

#####6， No Diaplay Blank Rows #####
设置是否显示无数据的行，下图示例展示的是分页行大小是25，但只显示了20条数据，无数据行没有显示：
 
![No Diaplay Blank Rows](http://git.oschina.net/bs2004/jquery.bsgrid/raw/master/WebContent/documention/images/jquery.bsgrid-06_no_diaplay_blank_rows.png)
 
实现代码：修改全局参数displayBlankRows，默认值为true
　　$.fn.bsgrid.defaults.displayBlankRows = false;
 

#####7， No Data #####
无数据时的提示：
 
![No Data](http://git.oschina.net/bs2004/jquery.bsgrid/raw/master/WebContent/documention/images/jquery.bsgrid-07_no_data.png)
 
注意此提示仅当$.fn.bsgrid.defaults.displayBlankRows = false;时才会显示，为true时显示的是空行。
说明：属性displayPagingToolbarOnlyMultiPages与displayBlankRows互不影响。
 

#####8， Grid With Checkbox #####
bsgrid内置并不支持checkbox的直接配置，通过column列的w_render属性实现：
 
![Grid With Checkbox](http://git.oschina.net/bs2004/jquery.bsgrid/raw/master/WebContent/documention/images/jquery.bsgrid-08_grid_with_checkbox.png)
 
实现代码：主要部分
   &lt;th w_render="checkbox" w_index="ID" width="3%;"&gt;&lt;input type="checkbox"/&gt;&lt;/th&gt;

   // 表格的checkbox选择
   if($('#searchTable tr:first th input[type=checkbox]').length == 1) {
       $('#searchTable tr:first th input[type=checkbox]').change(function () {
           if ($(this).attr('checked')) {
               $('#searchTable tr:not(:first) td input[type=checkbox]').attr('checked', true);
           } else {
               $('#searchTable tr:not(:first) td input[type=checkbox]').attr('checked', false);
           }
       });
   }

   function checkbox(record, rowIndex, colIndex, options) {
    	var headerTh = $.fn.bsgrid.getGridHeaderObject(options);
    	return '&lt;input type="checkbox" value="' + $.fn.bsgrid.parseData.getColumnValue(options.settings.dataType, record, $.trim(headerTh.eq(colIndex).attr(options.settings.colsProperties.indexAttr))) + '"/&gt;';
   }

   function getCheckedIds() {
       var ids = '';
       $('#searchTable tr:not(:first) td input:checked').each(function () {
           ids += ',' + $(this).val();
       });
       alert(ids.length > 0 ? ids.substring(1) : '');
   }
 

#####9， Grid With Little Paging #####
似ExtJS、EasyUI类分页工具条：
 
![Grid With Little Paging](http://git.oschina.net/bs2004/jquery.bsgrid/raw/master/WebContent/documention/images/jquery.bsgrid-09_grid_with_little_paging.png)
 
将grid.paging.min.css替换为grid.paging.little.min.css，并额外引入grid.paging.little.min.js（注意引用顺序），这个JS文件是对内置工具条展现的部分重写，简单的数几十行代码，充分体现了可扩展性特别强：
   &lt;link rel="stylesheet" href="../../builds/css/grid.paging.little.min.css"/&gt;
   &lt;script type="text/javascript" src="../../builds/js/grid.paging.little.min.js"&gt;&lt;/script&gt;
 

#####10， Standard Grid #####
演示bsgrid的大部分对外调用方法，并描述主要配置属性及其作用。
 
此处为了演示分页，后台使用jsp页面模拟分页数据，可以完整的展示排序，分页。
 
![Standard Grid](http://git.oschina.net/bs2004/jquery.bsgrid/raw/master/WebContent/documention/images/jquery.bsgrid-10_standard_grid.png)

#####11， Multi Grid #####
支持一个页面显示多个grid：
 
![Multi Grid](http://git.oschina.net/bs2004/jquery.bsgrid/raw/master/WebContent/documention/images/jquery.bsgrid-11_multi_grid.png)

#####12， Export Grid #####
bsgrid并不是提供导出Grid的页面数据功能，而是进行导出参数的组织：
 
![Export Grid](http://git.oschina.net/bs2004/jquery.bsgrid/raw/master/WebContent/documention/images/jquery.bsgrid-12_export_grid.png)
 
简单的grid导出参数URL类似如下：
http://bsgrid.oschina.mopaas.com/examples/grid/export.html?exportFileName=Export%2520Example&dataNames=XH%252CID%252CCHAR%252CTEXT%252CDATE%252CTIME%252CNUM&dataIndexs=XH,ID,CHAR,TEXT,DATE,TIME,NUM&dataLengths=50,50,150,300,150,150,50&dataAligns=center,center,left,left,center,center,center&param1=param1&param2=param2

需要额外引用用于导出的JS：
    &lt;script type="text/javascript" src="../../builds/js/export.min.js"&gt;&lt;/script&gt;

代码实现，如下，静态页面部分仅再需要增加一个导出按钮即可：
    var gridObj;
    $(function () {
        gridObj = $.fn.bsgrid.init('searchTable', {
            url: 'data/simple.json',
            pageSizeSelect: true,
            pageSize: 10
        });
    });

    function doExport() {
        alert('Only test request params, To see it in browser address url.');
        gridObj.options.otherParames = $('#searchForm').serializeArray();
        $.bsgrid_export.doExport($('#searchTable tr th'), gridObj.options.otherParames, {
            url: 'export.html', // only test request params
            exportFileName: 'Export Example',
            colsProperties: {
                width: 120
            },
            colWidthPercentmultiplier: 10 // if set column width N%, then column width will reset N*10, default 14
        });
    }
 

#####13， Grid with ArtDialog #####
结合artDialog，演示使用artDialog的锁屏遮罩样式，以及演示使用artDialog覆盖JS原生alert、confirm、prompt方法的使用。
 
 特别注意： 
 &emsp;&emsp;JS原生的alert、confirm、prompt方法是阻塞的，而使用artDialog覆盖的alert、confirm、prompt方法是非阻塞的，artDialog覆盖的方法是用回调方式实现阻塞的等待执行代码效果，详细可参看示例：[Pop with ArtDialog](http://bsgrid.oschina.mopaas.com/examples/artDialog/pop.html)
 
![Grid with ArtDialog](http://git.oschina.net/bs2004/jquery.bsgrid/raw/master/WebContent/documention/images/jquery.bsgrid-13_grid_with_artDialog.png)
 
需要额外引用的文件：
    &lt;link rel="stylesheet" href="../../plugins/artDialog/skins/blue.css"/&gt;
    &lt;link rel="stylesheet" href="override/artDialog.skins.override.css"/&gt;
    &lt;script type="text/javascript" src="../../plugins/artDialog/jquery.artDialog.min.js"&gt;&lt;/script&gt;
    &lt;script type="text/javascript" src="../../plugins/artDialog/artDialog.plugins.min.js"&gt;&lt;/script&gt;
    &lt;script type="text/javascript" src="override.grid.js"&gt;&lt;/script&gt;
    &lt;script type="text/javascript" src="override/artDialog.plugin.override.en.js"&gt;&lt;/script&gt;
    &lt;script type="text/javascript" src="override/artDialog.plugin.override.js"&gt;&lt;/script&gt;
    &lt;script type="text/javascript" src="override.pop.js"&gt;&lt;/script&gt;

artDialog需要引用的文件：artDialog/skins/blue.css、artDialog/jquery.artDialog.min.js、artDialog/artDialog.plugins.min.js
覆盖bsgrid的锁屏遮罩样式的文件：override.grid.js
覆盖JS原生的alert、confirm、prompt方法的文件：artDialog.skins.override.css、artDialog.plugin.override.en.js、artDialog.plugin.override.js、override.pop.js
 

#####14， Grid And Form with ArtDialog #####
结合ArtDialog使用，可以完成一个很好看的CRUD功能，详细可查看示例及示例源码：
 
![Grid with ArtDialog](http://git.oschina.net/bs2004/jquery.bsgrid/raw/master/WebContent/documention/images/jquery.bsgrid-14_grid_and_form_with_artDialog.png)

 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)