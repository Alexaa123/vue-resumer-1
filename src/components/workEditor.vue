<template>
	<div>
		<h2>工作经历</h2>
		<el-form>
			<div class="wrap" v-for="(wrok,index) in workHistory">
				<el-form-item label="公 司">
					<el-input v-model="wrok.company" placeholder="请输入公司名称"></el-input>
					</el-form-item>
					<el-form-item label="工作内容">
					<el-input
					  type="textarea"
					  :rows="6"
					  placeholder="请输入内容"
					  v-model="wrok.content">
					</el-input>
					</el-form-item>
					<i class="el-icon-error colse" v-on:click="removeWork(index)"></i>
			</div>
			<el-button class="addbtn" type="primary" v-on:click="addWork">添加</el-button>	
		</el-form>
	</div>
</template>

<script>
	export default{
		props: ['workHistory'],
		methods:{
			addWork(){
				this.workHistory.push({
					company: '', content: ''
				})
			},
			removeWork(index){
				this.workHistory.splice(index,1)
			}
		}	
	}
</script>