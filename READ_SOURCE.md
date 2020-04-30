
# 源码分析

## 文件结构

``` bash
/Users/liufang/openSource/FunnyLiu/vuex
├── CHANGELOG.md
├── LICENSE
├── README.md
├── dist
|  ├── logger.d.ts
|  ├── logger.js
|  ├── vuex.common.js
|  ├── vuex.esm.browser.js
|  ├── vuex.esm.browser.min.js
|  ├── vuex.esm.js
|  ├── vuex.js
|  └── vuex.min.js
├── docs
|  ├── README.md
|  ├── api
|  |  └── README.md
|  ├── fr
|  |  ├── README.md
|  |  ├── api
|  |  |  └── README.md
|  |  ├── guide
|  |  |  ├── README.md
|  |  |  ├── actions.md
|  |  |  ├── forms.md
|  |  |  ├── getters.md
|  |  |  ├── hot-reload.md
|  |  |  ├── modules.md
|  |  |  ├── mutations.md
|  |  |  ├── plugins.md
|  |  |  ├── state.md
|  |  |  ├── strict.md
|  |  |  ├── structure.md
|  |  |  └── testing.md
|  |  └── installation.md
|  ├── guide
|  |  ├── README.md
|  |  ├── actions.md
|  |  ├── forms.md
|  |  ├── getters.md
|  |  ├── hot-reload.md
|  |  ├── modules.md
|  |  ├── mutations.md
|  |  ├── plugins.md
|  |  ├── state.md
|  |  ├── strict.md
|  |  ├── structure.md
|  |  └── testing.md
|  ├── installation.md
|  ├── ja
|  |  ├── README.md
|  |  ├── api
|  |  |  └── README.md
|  |  ├── guide
|  |  |  ├── README.md
|  |  |  ├── actions.md
|  |  |  ├── core-concepts.md
|  |  |  ├── forms.md
|  |  |  ├── getters.md
|  |  |  ├── hot-reload.md
|  |  |  ├── modules.md
|  |  |  ├── mutations.md
|  |  |  ├── plugins.md
|  |  |  ├── state.md
|  |  |  ├── strict.md
|  |  |  ├── structure.md
|  |  |  └── testing.md
|  |  └── installation.md
|  ├── kr
|  |  ├── README.md
|  |  ├── api
|  |  |  └── README.md
|  |  ├── guide
|  |  |  ├── README.md
|  |  |  ├── actions.md
|  |  |  ├── forms.md
|  |  |  ├── getters.md
|  |  |  ├── hot-reload.md
|  |  |  ├── modules.md
|  |  |  ├── mutations.md
|  |  |  ├── plugins.md
|  |  |  ├── state.md
|  |  |  ├── strict.md
|  |  |  ├── structure.md
|  |  |  └── testing.md
|  |  └── installation.md
|  ├── ptbr
|  |  ├── README.md
|  |  ├── api
|  |  |  └── README.md
|  |  ├── guide
|  |  |  ├── README.md
|  |  |  ├── actions.md
|  |  |  ├── core-concepts.md
|  |  |  ├── forms.md
|  |  |  ├── getters.md
|  |  |  ├── hot-reload.md
|  |  |  ├── modules.md
|  |  |  ├── mutations.md
|  |  |  ├── plugins.md
|  |  |  ├── state.md
|  |  |  ├── strict.md
|  |  |  ├── structure.md
|  |  |  └── testing.md
|  |  └── installation.md
|  ├── ru
|  |  ├── README.md
|  |  ├── api
|  |  |  └── README.md
|  |  ├── guide
|  |  |  ├── README.md
|  |  |  ├── actions.md
|  |  |  ├── forms.md
|  |  |  ├── getters.md
|  |  |  ├── hot-reload.md
|  |  |  ├── modules.md
|  |  |  ├── mutations.md
|  |  |  ├── plugins.md
|  |  |  ├── state.md
|  |  |  ├── strict.md
|  |  |  ├── structure.md
|  |  |  └── testing.md
|  |  └── installation.md
|  └── zh
|     ├── README.md
|     ├── api
|     |  └── README.md
|     ├── guide
|     |  ├── README.md
|     |  ├── actions.md
|     |  ├── forms.md
|     |  ├── getters.md
|     |  ├── hot-reload.md
|     |  ├── modules.md
|     |  ├── mutations.md
|     |  ├── plugins.md
|     |  ├── state.md
|     |  ├── strict.md
|     |  ├── structure.md
|     |  └── testing.md
|     └── installation.md
├── docs-gitbook
|  ├── LANGS.md
|  ├── assets
|  |  ├── CNAME
|  |  ├── circle.yml
|  |  └── vuex.ai
|  ├── book.json
|  ├── en
|  |  └── book.json
|  ├── fr
|  |  ├── README.md
|  |  ├── SUMMARY.md
|  |  ├── actions.md
|  |  ├── api.md
|  |  ├── book.json
|  |  ├── core-concepts.md
|  |  ├── forms.md
|  |  ├── getters.md
|  |  ├── getting-started.md
|  |  ├── hot-reload.md
|  |  ├── images
|  |  |  ├── flow.png
|  |  |  └── vuex.png
|  |  ├── installation.md
|  |  ├── intro.md
|  |  ├── modules.md
|  |  ├── mutations.md
|  |  ├── plugins.md
|  |  ├── state.md
|  |  ├── strict.md
|  |  ├── structure.md
|  |  └── testing.md
|  ├── gitbook
|  |  └── images
|  |     └── favicon.ico
|  ├── ja
|  |  ├── README.md
|  |  ├── SUMMARY.md
|  |  ├── actions.md
|  |  ├── api.md
|  |  ├── book.json
|  |  ├── core-concepts.md
|  |  ├── forms.md
|  |  ├── getters.md
|  |  ├── getting-started.md
|  |  ├── hot-reload.md
|  |  ├── images
|  |  |  ├── flow.png
|  |  |  └── vuex.png
|  |  ├── installation.md
|  |  ├── intro.md
|  |  ├── modules.md
|  |  ├── mutations.md
|  |  ├── plugins.md
|  |  ├── state.md
|  |  ├── strict.md
|  |  ├── structure.md
|  |  └── testing.md
|  ├── kr
|  |  ├── README.md
|  |  ├── SUMMARY.md
|  |  ├── actions.md
|  |  ├── api.md
|  |  ├── book.json
|  |  ├── forms.md
|  |  ├── getters.md
|  |  ├── getting-started.md
|  |  ├── hot-reload.md
|  |  ├── images
|  |  |  ├── flow.png
|  |  |  └── vuex.png
|  |  ├── installation.md
|  |  ├── intro.md
|  |  ├── modules.md
|  |  ├── mutations.md
|  |  ├── plugins.md
|  |  ├── state.md
|  |  ├── strict.md
|  |  ├── structure.md
|  |  └── testing.md
|  ├── old
|  |  ├── README.md
|  |  └── SUMMARY.md
|  ├── pt-br
|  |  ├── README.md
|  |  ├── SUMMARY.md
|  |  ├── actions.md
|  |  ├── api.md
|  |  ├── book.json
|  |  ├── core-concepts.md
|  |  ├── forms.md
|  |  ├── getters.md
|  |  ├── getting-started.md
|  |  ├── hot-reload.md
|  |  ├── images
|  |  |  ├── flow.png
|  |  |  └── vuex.png
|  |  ├── installation.md
|  |  ├── intro.md
|  |  ├── modules.md
|  |  ├── mutations.md
|  |  ├── plugins.md
|  |  ├── state.md
|  |  ├── strict.md
|  |  ├── structure.md
|  |  └── testing.md
|  ├── ru
|  |  ├── README.md
|  |  ├── SUMMARY.md
|  |  ├── actions.md
|  |  ├── api.md
|  |  ├── book.json
|  |  ├── core-concepts.md
|  |  ├── forms.md
|  |  ├── getters.md
|  |  ├── getting-started.md
|  |  ├── hot-reload.md
|  |  ├── images
|  |  |  ├── flow.png
|  |  |  └── vuex.png
|  |  ├── installation.md
|  |  ├── intro.md
|  |  ├── modules.md
|  |  ├── mutations.md
|  |  ├── plugins.md
|  |  ├── state.md
|  |  ├── strict.md
|  |  ├── structure.md
|  |  └── testing.md
|  └── zh-cn
|     ├── book.json
|     └── images
|        ├── flow.png
|        └── vuex.png
├── examples
|  ├── chat
|  |  ├── api
|  |  |  ├── index.js
|  |  |  └── mock-data.js
|  |  ├── app.js
|  |  ├── components
|  |  |  ├── App.vue
|  |  |  ├── Message.vue
|  |  |  ├── MessageSection.vue
|  |  |  ├── Thread.vue
|  |  |  └── ThreadSection.vue
|  |  ├── css
|  |  |  └── chat.css
|  |  ├── index.html
|  |  └── store
|  |     ├── actions.js
|  |     ├── getters.js
|  |     ├── index.js
|  |     └── mutations.js
|  ├── counter
|  |  ├── Counter.vue
|  |  ├── app.js
|  |  ├── index.html
|  |  └── store.js
|  ├── counter-hot
|  |  ├── CounterControls.vue
|  |  ├── app.js
|  |  ├── index.html
|  |  └── store
|  |     ├── actions.js
|  |     ├── getters.js
|  |     ├── index.js
|  |     └── mutations.js
|  ├── global.css
|  ├── index.html
|  ├── server.js
|  ├── shopping-cart
|  |  ├── api
|  |  |  └── shop.js
|  |  ├── app.js
|  |  ├── components
|  |  |  ├── App.vue
|  |  |  ├── ProductList.vue
|  |  |  └── ShoppingCart.vue
|  |  ├── currency.js
|  |  ├── index.html
|  |  └── store
|  |     ├── index.js
|  |     └── modules
|  |        ├── cart.js
|  |        └── products.js
|  ├── todomvc
|  |  ├── app.js
|  |  ├── components
|  |  |  ├── App.vue
|  |  |  └── TodoItem.vue
|  |  ├── index.html
|  |  └── store
|  |     ├── actions.js
|  |     ├── index.js
|  |     ├── mutations.js
|  |     └── plugins.js
|  └── webpack.config.js
├── package.json
├── rollup.config.js
├── rollup.logger.config.js
├── rollup.main.config.js
├── scripts
|  ├── build-logger.js
|  ├── build-main.js
|  ├── build.js
|  └── release.sh
├── src
|  ├── helpers.js
|  ├── index.cjs.js
|  ├── index.js
|  ├── mixin.js
|  ├── module
|  |  ├── module-collection.js
|  |  └── module.js
|  ├── plugins
|  |  ├── devtool.js
|  |  └── logger.js
|  ├── store.js
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
  