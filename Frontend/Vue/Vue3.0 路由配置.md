

# Vue3.0 路由配置

配置前先安装`vue-router`，当前使用的版本是4.0.13

然后先创建一个路由的js文件，一般放在`src/router/index.js`

`index.js`文件如下

```js
import PageView from '../views/Page'  // 需要插入到路由的界面
import {createRouter} from "vue-router";
import {createWebHistory} from "vue-router/dist/vue-router.cjs.prod";

const routes = [
    {
        path: '/',
        component: PageView
    }
]

const router = createRouter({
    history: createWebHistory(process.env.BASE_URL),
    routes
})

export default router;
```

然后在`main.js`中使用这个`router`

```js
import { createApp } from 'vue'
import App from './App.vue'
import router from "@/router";

const app = createApp(App)

app.use(router)
app.mount('#app')
```

