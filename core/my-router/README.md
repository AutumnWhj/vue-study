vue-router路由实现
分析：
从Vue.use(VueRouter) 可知 实现的router最终暴露的是一个插件的形式供vue使用，因此要实现一个install方法。
new VueRouter，VueRouter是一个class类，类中实现路由定义的方法，如push,go,back。
this.$router获取路由的实例，因此要在原型链上绑定$router。
<router-view/>与<router-link>，实现全局组件
不同的url在不刷新的情况下，匹配不同的页面，因此url应是响应式的，并且根据不同url通过路由表匹配不同的component。

实现要点：
1、install vue的插件形式调用
2、vueRouter类的实现
3、全局组件的实现
4、监听url，并实现响应式
5、路由api的实现push,go,back,matched