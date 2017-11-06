<template>
	<div id="preview">
		<h1>{{resume.profile.name || '请填写名称'}}</h1>
		<h1>{{resume.profile.city || '请填写城市'}}</h1>
		<h1>{{resume.profile.birth || '请填写生日'}}</h1>

		<section v-if="filter(resume.workHistory).length > 0">
			<h2>工作经历</h2>
			<ul>
				<li v-for="workHistory in filter(resume.workHistory)">
					<p>{{workHistory.company}}</p>
					<p>{{workHistory.time}}至少</p>
					<p>{{workHistory.time2}}</p>
					<p>{{workHistory.content}}</p>
				</li>
			</ul>
		</section>
<!-- 		<h1>{{resume.workHistory[0].time}}</h1>
		<h1>{{resume.workHistory[0].time2}}</h1>
		<h1>{{resume.items[0].duration}}</h1>
		<h1>{{resume.items[0].duration2}}</h1> -->
	</div>
</template>

<style>
	#preview{
		
	}
</style>

<script>
	export default{
		props:['resume'],
		methods:{
			filter(arr){//找出非空对象 只要有一个value不是false 就返回 false
				return arr.filter(item=>!this.isEmpty(item))
			},
			isEmpty(obj){
				let empty = true
				for(let key in obj){
					if (obj[key]) {
						empty = false
						break
					}
				}
				return empty
			}
		}
	}
</script>