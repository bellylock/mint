<template>
	<div class="hello">
		<p>{{msg}}</p>
		<div>
			<mt-tab-container v-model="active">
			  <mt-tab-container-item id="tab-container1">
			    <mt-cell v-for="n in 1" title="tab-container1">{{n}}</mt-cell>
			  </mt-tab-container-item>
			  <mt-tab-container-item id="tab-container2">
			    <mt-cell v-for="n in 2" title="tab-container2">{{n}}</mt-cell>
			  </mt-tab-container-item>
			  <mt-tab-container-item id="tab-container3">
			    <mt-cell v-for="n in 3" title="tab-container3">{{n}}</mt-cell>
			  </mt-tab-container-item>
			  <mt-tab-container-item id="tab-container4">
			    <mt-cell v-for="n in 4" title="tab-container4">{{n}}</mt-cell>
			  </mt-tab-container-item>
			</mt-tab-container>
		</div>
		<div>
			<mt-tabbar v-model="selected">
			  <mt-tab-item id="外卖">
				  <span @click="pick('外卖')">外卖</span>
			  </mt-tab-item>
			  <mt-tab-item id="订单">
				  <span @click="pick('订单')">订单</span>
			  </mt-tab-item>
			  <mt-tab-item id="发现">
				  <span @click="pick('发现')">发现</span>
			  </mt-tab-item>
			  <mt-tab-item id="我的">
				  <span @click="pick('我的')">我的</span>
			  </mt-tab-item>
			</mt-tabbar>
		</div>
	</div>
</template>

<script>
	import { TabContainer, TabContainerItem } from 'mint-ui';
	import { Tabbar, TabItem } from 'mint-ui';
	import { Indicator } from 'mint-ui';
	export default {
		name: 'HelloWorld',
		data() {
			return {
				msg: 'Welcome111',
				active: 'tab-container1',
				selected: '外卖'
			}
		},
		// mounted() {},
		methods:{
			open() {
				Indicator.open('加载中...');
			},
			close() {
				Indicator.close();
			},
			pick(name) {
				this.selected = name
			}
		},
		watch: {
			selected:function(selected){
				if (selected == '外卖') {
					this.active = 'tab-container1'
				}
				if (selected == '订单') {
					this.active = 'tab-container2'
				}
				if (selected == '发现') {
					this.active = 'tab-container3'
				}
				if (selected == '我的') {
					this.active = 'tab-container4'
				}
			}
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped type="text/css">
	.hello{
		background: pink;
		p{
			font-size: 16px;
			color: blue;
		}
	}
	
	
</style>
