    npm install -g vue-cli
    vue init nuxt/starter <project-name>
    //vue init nuxt-community/starter-template
    
    cd <project-name>
    npm install
    npm run dev


# async: #	
1、函数内部return语句返回的值，会成为then方法回调函数的参数。
2、ES5里面没有this,它们的this都是最外层的函数的this
3、箭头函数没有自己的this，所以当然也就不能用call()、apply()、bind()这些方法去改变this的指向

    // 函数声明
    async function foo() {}
    
    // 函数表达式
    const foo = async function () {};
    
    // 对象的方法
    let obj = { async foo() {} };
    obj.foo().then(...)
    
    // Class 的方法
    class Storage {
      constructor() {
    this.cachePromise = caches.open('avatars');
      }
    
      async getAvatar(name) {
    const cache = await this.cachePromise;
    return cache.match(`/avatars/${name}.jpg`);
      }
    }
    
    const storage = new Storage();
    storage.getAvatar('jake').then(…);
    
    // 箭头函数
    const foo = async () => {};

# element-ui #

1、

    npm install element-ui -S

2、 #nuxt.config.js
	
	loading: { color: '#3B8070' },
    
    plugins: [{
        src: '~plugins/ElementUI',//引入文件
        ssr: true,
    }],
    css: [
        'element-ui/lib/theme-chalk/index.css'
    ],


	build: {
        /*
         ** Run ESLint on save
         */
        extend(config, { isDev, isClient }) {
            if (isDev && isClient) {
                config.module.rules.push({
                    enforce: 'pre',
                    test: /\.(js|vue)$/,
                    loader: 'eslint-loader',
                    exclude: /(node_modules)/
                })
            }

			//   重点在这里。。。。。。。。。。。。。。。。。。。。。。。。。。。。
        	vendor: ['element-ui'] //防止element-ui被打包多次
        },
    }

# jade、sass、pug #

	//安装支持pug,jade依赖
    npm install pug pug-loader pug-filters jade jade-loader node-sass sass-loader vue-style-loader --save-dev

    module.exports = {
      css: [

		/******************不要必须的，可以不写**********************/

	    // 加载一个节点。js模块直接(这里是一个Sass文件)
	    'bulma',
	
	    // 项目中的CSS文件
	    '@/assets/css/main.css',
	
	    // 项目中的sCSS文件
	    '@/assets/css/main.scss'
      ]
    }


# jade、sass、pug、element-ui #

    npm install pug pug-loader pug-filters jade jade-loader node-sass sass-loader vue-style-loader element-ui --save-dev