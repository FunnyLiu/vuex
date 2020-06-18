# Vuex [![Build Status](https://circleci.com/gh/vuejs/vuex/tree/dev.png?style=shield)](https://circleci.com/gh/vuejs/vuex)




# 源码分析

## 文件结构

``` bash
├── src
|  ├── helpers.js
|  ├── index.cjs.js
|  ├── index.js - 入口文件
|  ├── mixin.js
|  ├── module
|  |  ├── module-collection.js
|  |  └── module.js
|  ├── plugins
|  |  ├── devtool.js
|  |  └── logger.js
|  ├── store.js - install方法和Store类，保证单例store
|  └── util.js
├── types
|  ├── README.md
|  ├── helpers.d.ts
|  ├── index.d.ts
|  ├── tsconfig.json
|  └── vue.d.ts
└── yarn.lock

directory: 66 file: 324

ignored: directory (2)

```

## 外部模块依赖

请在： http://npm.broofa.com?q=vuex 查看

## 内部模块依赖

![img](./inner.svg)
  

## 知识点

### subscribeAction，在 action 被调用前后插入一些逻辑 aop原理

相关api用法参考：[API 参考 | Vuex](https://vuex.vuejs.org/zh/api/#subscribeaction)。

通过api调用genericSubscribe，完成对action订阅者列表的增加
``` js
// 定义action的前后拦截器
subscribeAction (fn, options) {
  // 如果fn为一个函数，则默认是before
  const subs = typeof fn === 'function' ? { before: fn } : fn
  return genericSubscribe(subs, this._actionSubscribers, options)
}

```

然后在执行action时去aop的兼容before和after：

``` js
try {
  //首先执行before函数列表
  this._actionSubscribers
    .slice() // shallow copy to prevent iterator invalidation if subscriber synchronously calls unsubscribe
    .filter(sub => sub.before)
    .forEach(sub => sub.before(action, this.state))
} catch (e) {
  if (__DEV__) {
    console.warn(`[vuex] error in before action subscribers: `)
    console.error(e)
  }
}
// 执行针对从处理函数等等
const result = entry.length > 1
  ? Promise.all(entry.map(handler => handler(payload)))
  : entry[0](payload)

return result.then(res => {
  try {
    // 再执行after函数列表
    this._actionSubscribers
      .filter(sub => sub.after)
      .forEach(sub => sub.after(action, this.state))
  } catch (e) {
    if (__DEV__) {
      console.warn(`[vuex] error in after action subscribers: `)
      console.error(e)
    }
  }
  return res
})
```





> Centralized State Management for Vue.js.

<p align="center">
  <img width="700px" src="https://raw.githubusercontent.com/vuejs/vuex/dev/docs/.vuepress/public/vuex.png">
</p>

- [What is Vuex?](https://vuex.vuejs.org/)
- [Full Documentation](http://vuex.vuejs.org/)

## Examples

- [Counter](https://github.com/vuejs/vuex/tree/dev/examples/counter)
- [Counter with Hot Reload](https://github.com/vuejs/vuex/tree/dev/examples/counter-hot)
- [TodoMVC](https://github.com/vuejs/vuex/tree/dev/examples/todomvc)
- [Flux Chat](https://github.com/vuejs/vuex/tree/dev/examples/chat)
- [Shopping Cart](https://github.com/vuejs/vuex/tree/dev/examples/shopping-cart)

Running the examples:

``` bash
$ npm install
$ npm run dev # serve examples at localhost:8080
```

## Contribution

Please make sure to read the [Contributing Guide](https://github.com/vuejs/vuex/blob/dev/.github/contributing.md) before making a pull request.

## License

[MIT](http://opensource.org/licenses/MIT)
