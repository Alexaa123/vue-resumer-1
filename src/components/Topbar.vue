<template>
	<div id="topbar">
		<span class="logo">Resumer</span>
		<div class="actions">
			<el-button type="success">登陆</el-button>
			<el-button type="primary">注册</el-button>
			<el-button type="danger" v-on:click="preview">预览</el-button>
		</div>
	</div>
</template>


<script>
	export default{
		methods:{
			preview(){
				this.$emit('preview')
			}
		}
	}
</script>

<style lang="scss">
	#topbar{
		display:flex;
		justify-content: space-between;
		align-items: center;
		padding:16px;
		font-size:20px;
		.logo{
			font-size: 32px;
		}
	}
</style>