<template>
	<div>
		<h2>个人信息</h2>
		<el-form class="wrap">
			<el-form-item label="姓 名">
				<el-input v-model="profile.name" placeholder="你的姓名"></el-input>
				</el-form-item>
				<el-form-item label="城 市">
				<el-input v-model="profile.city" placeholder="你所在的城市"></el-input>
				</el-form-item>
				<el-form-item label="出生年月">
				<el-input v-model="profile.birth" placeholder="你的出生年/月/日"></el-input>
				</el-form-item>
		</el-form>
	</div>
</template>

<script>
	export default {
		props: ['profile']
	}
</script>