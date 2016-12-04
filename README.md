# 插件历程

1. 遇到的问题
    1. 插件内的 vue 有bug，带 component 的 vue 实例 init 和 ready 的方法不会被调用
    2. component 里的 ready 方法不会被调用
2. 插件的名称命名为 Binding Tree
3. 全称为 Abos Binding Tree
4. 插件完成之后应该做到的事情
    > /main.js 一般不修改，除非要加新功能
    > /panel/index.js 一般不修改，除非要加新功能
    > /tools/plugin.js 类是底层类， 不做任何修改
    > /panel/plugin-panel.js 里进行根页面的逻辑编写
    > /panel/plugin-panel.html 样式一般写在这里， 首页的样式也写在这里
    > 各种数据的初始化， 可以直接在组件的 data 方法里获取
    > Vue 的组件逻辑， html 可以自由放， 一般推荐 /panel/components, /panel/html
    > 而且 Vue 的 组件会自动注册， 只需要在 package.json 里配置就好
        > aplugin._pkg.abosPlugin.vue.resources = {
        >     name: 'compo-name',
        >     html: 'html-path-rooted-from-package',
        >     js: 'js-path-rooted-from-package',
        > }
