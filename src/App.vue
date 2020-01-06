<template>
	<div id="app">
		<!-- <img src="./assets/logo.png"> -->
		<router-view />
	</div>
</template>

<script>
	export default {
		name: 'App'
	}
</script>

<style>
	* {
		margin: 0;
		padding: 0;
		list-style: none;
		box-sizing: border-box;
		/* 禁用长按选中文本功能 */
		-webkit-touch-callout: none;
		-webkit-user-select: none;
		-khtml-user-select: none;
		-moz-user-select: none;
		-ms-user-select: none;
		user-select: none;
	}

	#app {
		font-family: 'Avenir', Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		color: #2c3e50;
		margin-top: 60px;
	}
</style>
