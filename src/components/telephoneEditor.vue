<template>
	<div>
		<h2>联系方式</h2>
		<el-form>
			<div class="wrap" v-for="(item,index) in telephone">
				<el-form-item label="电话">
					<el-input v-model="item.number" placeholder="number"></el-input>
				</el-form-item>

				<el-form-item label="微信">
					<el-input v-model="item.weixin" placeholder="weixin"></el-input>
				</el-form-item>

				<el-form-item label="QQ">
					<el-input v-model="item.QQ" placeholder="QQ"></el-input>
				</el-form-item>

				<el-form-item label="github">
					<el-input v-model="item.github" placeholder="github"></el-input>
				</el-form-item>
					
			</div>
		</el-form>
	</div>
</template>

<script>
	export default {
		props: ['telephone']
	}
</script>