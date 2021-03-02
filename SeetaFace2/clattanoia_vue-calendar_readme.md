# vue-calendar

基于vuejs+webpack环境使用的日期选择插件

[Live demo](http://jinzhe.github.io/vue-calendar/)

* 支持`单选`和`多选`日期
* 支持限定`开始`和`结束`日期范围选择。
* 支持小时分钟
* 支持一个页面多个实例
* 支持自定义星期和月份标题


![](http://ww1.sinaimg.cn/large/823603acgw1ez1n57t8jug20d40acwjw.gif)

![](http://ww3.sinaimg.cn/large/823603acgw1ez8ks5cudrg20in0badzn.gif)


# Options
* :show    是否显示
* :type    date|datetime
* :value	默认值
* :begin  可选开始时间
* :end    可选结束时间
* :x      显示x坐标
* :y      显示y坐标
* :range  是否多选
* :weeks	星期标题
* :months	月份标题
* :sep		分隔符

# How to use?

```
 
 
      
      
      

      
     

     
 
 

 
import calendar from "./calendar.vue"

export default {
    components:{
        calendar
    },
    data() {
        return {
            // 数据绑定
            calendar:{
                show:false,
                x:0,
                y:0,
                picker:"",
                type:"date",
                value:"",
                begin:"",
                end:"",
                value:"",
                sep:"/",
                weeks:[],
                months:[],
                range:false,
                items:{
                    // 单选模式
                    picker1:{
                        type:"date",
                        begin:"2016-08-20",
                        end:"2016-08-25",
                        value:"2016-08-21",
                        sep:"-",
                        weeks:['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat'],
                        months:['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
                    },
                    // 2个日期模式
                    picker2:{
                        type:"date",
                        value:"",
                        range:true,
                        sep:".",
                    },
                    // 日期时间模式
                    picker3:{
                        type:"datetime",
                        value:"",
                        sep:"-",
                    },
                    // 日期时间模式
                    picker4:{
                        type:"time",
                        value:"",
                    },
                }
            }
        }
    },
     // 处理值的传递
    watch:{
        'calendar.value': function (value) {
            this.calendar.items[this.calendar.picker].value=value
        }
    },  
    methods:{
        // 打开显示选择器
        open(e,type) {
            // 设置类型
            this.calendar.picker=type
            this.calendar.type=this.calendar.items[type].type
            this.calendar.range=this.calendar.items[type].range
            this.calendar.begin=this.calendar.items[type].begin
            this.calendar.end=this.calendar.items[type].end
            this.calendar.value=this.calendar.items[type].value
            // 可不用写
            this.calendar.sep=this.calendar.items[type].sep
            this.calendar.weeks=this.calendar.items[type].weeks
            this.calendar.months=this.calendar.items[type].months

            this.calendar.show=true
            this.calendar.x=e.target.offsetLeft
            this.calendar.y=e.target.offsetTop+e.target.offsetHeight+8
        }
    }
}
```
 
# Conatct

- Tencent QQ Group: 240319632
- E-mail: 129@jinzhe.net

 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)