## 浏览器资源监控
- window.performance.getEntriesByType("resource")
- window.performance.getEntriesByType("navigation")
## Event Loop(JS)
- [EventLoop](https://zhuanlan.zhihu.com/p/41543963)
## defineProperty(get和set的双向绑定实现)
```
var $watch=function(myObject,callback){
    initWatch(myObject);
    function initWatch(obj){
        for(var i in obj){
            if(typeof obj!='object'){
                return;
            }
            (function(value,o,attr){
                var v=value;
                var oldValue=value;
                Object.defineProperty(o,attr,{
                    get:function(){
                        return v;
                    },
                    set:function (newValue){
                        oldValue=v;
                        v=newValue;
                        callback(newValue,oldValue)
                    }
                });
            })(obj[i],obj,i);
            initWatch(obj[i]);
        }
    }
};
var a = {
　　count:'1',
　　count2:{
　　　　count2_1:'2_1',
　　　　count2_2:'2_2'
　　}
}
Object.prototype.setValue = function(key,value){//设置新Key数据
    this[key] = value;
    $watch(this,function(newValue,oldValue){
        console.log('旧数据~'+oldValue+'    '+'新数据~'+newValue);
    })
}
$watch(a,function(newValue,oldValue){
    console.log('旧数据'+oldValue+'    '+'新数据'+newValue);
})
```
## ow JS类型检查
- [ow](https://github.com/sindresorhus/ow)
- JavaScript 语言没有类型检查，运行时无法知道函数的参数是否为指定的类型。这个库就用来检查函数参数的类型，如果不符合要求就抛错。
## ES6
- [ES6](http://es6.ruanyifeng.com/)
## React/React-native
- [React](https://reactjs.org/)
- [React-native](https://facebook.github.io/react-native/)
## Vue
- [Vue](https://cn.vuejs.org/)
## Canvas
- [Canvas](https://github.com/supperjet/H5-Animation)
## 鲜为人知的JS
- [what the js is that](https://www.infoq.cn/article/QMteVFAMMeBpDhWE-m01)
## Prettier
- [Prettier](https://www.infoq.cn/article/IzAMXQtkJv3N0rXX_G6a)
## 团队建立
- [团队建立](https://www.infoq.cn/article/2kJpJl8*CPK3UZXHm2By)
## Flutter
- [Flutter]()
## 2019 React
- [React](https://www.infoq.cn/article/AEkiVAiJf25LZmoUe_yc)
## 2019 Node.js
- [Node.js](https://www.infoq.cn/article/mXd3WWq_8fd3xoEH9zjG)
