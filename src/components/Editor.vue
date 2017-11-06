<template>
	<div id="editor">
		<nav>
			<ol>
				<li class="active">
					<svg class="icon ">
    					<use xlink:href="#icon-zheng"></use>
					</svg>
				</li>
				<li>
					<svg class="icon">
    					<use xlink:href="#icon-work"></use>
					</svg>
				</li>
				<li>
					<svg class="icon">
    					<use xlink:href="#icon-book"></use>
					</svg>
				</li>
				<li>
					<svg class="icon">
    					<use xlink:href="#icon-jiang"></use>
					</svg>
				</li>
				<li>
					<svg class="icon">
    					<use xlink:href="#icon-poject"></use>
					</svg>
				</li>
				<li>
					<svg class="icon">
    					<use xlink:href="#icon-telephone"></use>
					</svg>
				</li>
			</ol>
		</nav>
		<ol>
			<li></li>
		</ol>
	</div>
</template>

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
			padding:8px 0;
			border:1px solid red;
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
	}
</style>