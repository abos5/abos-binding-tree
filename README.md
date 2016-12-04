# todo
1. Fixed window.aplugin global variable, Don't know what would happen if we have multi docking plugins.
2. Add node searching(which is not really important).
3. Make the UI look better.

# 插件历程

0. 插件的名字很难起， 应该叫什么
    1. abos-binding-tree 相对于我自己少了 ccc 的前缀, 可能会与其他项目冲突(最终决定这个了， 如果与自己的项目冲突可以重新起名字， 但与ccc的冲突就改不了了)
    2. ccc-binding-tree  相对于ccc 少了我个人的前缀， 可能会与其他开发冲突
    3. abos-ccc-binding-tree 又很啰嗦
1. 遇到的问题
    1. 插件内的 vue 有bug，带 component 的 vue 实例 init 和 ready 的方法不会被调用
    2. component 里的 ready 方法不会被调用
2. 插件的名称命名为 Binding Tree
3. 全称为 Abos Binding Tree
4. 插件完成之后应该做到的事情

    > /main.js 一般不修改，除非要加新功能

    > /panel/index.js 一般不修改，除非要加新功能, 比如加入 IPC 消息等

    > /tools/plugin.js 类是底层类， 不做任何修改

    > /panel/plugin-panel.js 里进行根页面的逻辑编写

    > /panel/plugin-panel.html 样式一般写在这里， 首页的样式也写在这里

    > 各种数据的初始化， 可以直接在组件的 data 方法里获取

    > Vue 的组件逻辑， html 可以自由放， 一般推荐 /panel/components, /panel/html

    > 而且 Vue 的 组件会自动注册， 只需要在 package.json 里配置就好

    ```javascript
        aplugin._pkg.abosPlugin.vue.resources = {
            name: 'compo-name',
            html: 'html-path-rooted-from-package',
            js: 'js-path-rooted-from-package',
        }
    ```






