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
				<profileEditor v-bind:profile="profile" />
			</li>
			<li v-bind:class="{active:currentTab == 1}">
				<workEditor v-bind:workHistory="workHistory" />
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
	import ProfileEditor from './profileEditor'
	import WorkEditor from './workEditor'
	export default {
		components:{
			ProfileEditor,
			WorkEditor
		},
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
				padding:24px;
				display:none;
				height:100%;
				overflow: auto;
			.wrap{
				margin:24px 0;
				position:relative;
				border-radius:5px;
				background:rgba(0,0,0,0.02);
				box-shadow:0 0 3px hsla(0,0,0,0.3);
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