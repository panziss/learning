# nuxt: #

- 文件路径前面/  用~代替
- 路由：隐藏路由，在文件名前加 _
----------
    npm install -g vue-cli
    vue init nuxt/starter <project-name>
    cd <project-name>
    npm install
    npm run dev

# vuex #

    npm i vuex --save

在 src 下新建文件夹 vuex，进入 vuex 新建 store.js


然后去 main.js 加入，import store from './vuex/store'


再修改 Vue 实例如下


    new Vue({
	  el: '#app',
	  router,
	  store,
	  render: h => h(App)
	})

去新建的 store.js

    import Vue  from 'vue';
	import Vuex from 'vuex';
	Vue.use(Vuex)
	export default new Vuex.Store({
	  state: {
	    platform: ''
	  },
	  mutations: {
	    SET_APP(state, platform) {
	      state.platform = platform;
	    }
	  },
	  actions: {
	    setApp({commit}, platform) {
	      commit('SET_APP', platform);
	    }
	  },
	  getters: {
	    getApp: (state) => state.platform
	  }
	})

	export default new Vuex.Store({
	    state
	})



# vue: #
    export default {
		data() {

		},
		props:{
		
		},
		methods:{
		
		},
		computed:{
		
		},
		components:{
		
		}
	}


select   多选时，<select multiple></select>

<input type="number" v-model.number="age" /> :  加上v-model.number时html返回的就是数字了，不是字符串了

做全选和反选时逻辑：把全选和反选按钮   




