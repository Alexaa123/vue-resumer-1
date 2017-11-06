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
			<li v-bind:class="{active:currentTab == 0}">tab1</li>
			<li v-bind:class="{active:currentTab == 1}">tab2</li>
			<li v-bind:class="{active:currentTab == 2}">tab3</li>
			<li v-bind:class="{active:currentTab == 3}">tab4</li>
			<li v-bind:class="{active:currentTab == 4}">tab5</li>
			<li v-bind:class="{active:currentTab == 5}">tab6</li>
		</ol>
	</div>
</template>

<script>
	export default {
		data(){
			return {
				currentTab:0,
				icons:['zheng','work','book','jiang','poject','telephone']
			}
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
			>li{
				display:none;
				&.active{
					display:block;
				}
			}
		}
	}
</style>