<template>
	<div id="editor">
		<nav>
			<ol>
				<li 
				v-for = "i in [0,1,2,3,4,5]"
				v-bind:class = "{active:currentTab == i}"
				v-on:click = "currentTab = i"
				>
					<svg class="icon ">
    					<use v-bind:xlink:href="`#icon-${icons[i]}`"></use>
					</svg>
				</li>				
			</ol>
		</nav>
		<ol class="panes">
			<li v-bind:class="{active:currentTab == 0}">
				<h2>个人信息</h2>
				<el-form>
					<el-form-item label="姓 名">
    					<el-input v-model="profile.name"></el-input>
  					</el-form-item>
  					<el-form-item label="城 市">
    					<el-input v-model="profile.city"></el-input>
  					</el-form-item>
  					<el-form-item label="出生年月">
    					<el-input v-model="profile.birth"></el-input>
  					</el-form-item>
				</el-form>
			</li>
			<li v-bind:class="{active:currentTab == 1}">
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
			</li>
			<li v-bind:class="{active:currentTab == 2}">
				<h2>学习经历</h2>
			</li>
			<li v-bind:class="{active:currentTab == 3}">
				<h2>获奖情况</h2>
			</li>
			<li v-bind:class="{active:currentTab == 4}">
				<h2>项目信息</h2>
			</li>
			<li v-bind:class="{active:currentTab == 5}">
				<h2>联系方式</h2>
			</li>
		</ol>
	</div>
</template>

<script>
	export default {
		data(){
			return {
				currentTab:0,
				icons:['zheng','work','book','jiang','poject','telephone'],
				profile:{
					name:'',
					city:'',
					birth:''
				},
				workHistory:[
					{company: '', content: ''}
				]
			}
		},
		methods:{
			addWork(){
				this.workHistory.push({
					company: '', content: ''
				})
			},
			removeWork(index){
				this.workHistory.splice(index,1)
			}
		},
		created(){

		}
	}
</script>

<style lang="scss">
	#editor{
		text-align:center;
		min-height:80px;
		display: flex;
		> nav{
			background:#222;
			width:6em;
		}
		nav > ol > li{
			cursor: pointer;
			padding:16px 0;
			 > .icon{
			 	fill: #fff;
			 }
			 &.active{
			 	background:#fff;
			 	>.icon{
			 		fill: #111;
			 	}
			 }
		}
		> .panes{
			flex:1;
			>li{
				text-align: left;
				padding:32px;
				display:none;
				height:100%;
				overflow: auto;
			.wrap{
				margin:24px 0;
				position:relative;

				border-radius:5px;
				background:rgba(0,0,0,0.05);
				box-shadow:0 0 3px hsla(0,0,0,0.2);
				}
			.addbtn{
				display: block;
				margin:0 auto;
			}
			.colse{
				cursor: pointer;
				position: absolute;
				top:4px;
				right:4px;
				font-size:1.4em;
				color:rgba(0,0,0,0.3);
				&:hover{
					color:red;
				}
			}	
				&.active{
					display:block;
				}
			}
		}
	}
</style>