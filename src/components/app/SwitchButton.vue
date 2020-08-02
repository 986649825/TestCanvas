<template>

	<div class="SwitchButton">
		<div class="backGround">
		</div>
		<div class="turn" :style="{left:isTrue==true? '1.5rem':'0rem'}" :class="{'turnGo' : isTrue&&open, 'turnBack': (!isTrue)&&open}"
		 @click="turn()"></div>
	</div>
</template>

<script>
	export default {
		props: {},
		data: function() {
			return {
				isTrue: false, //动画控制
				open: false, //限制开始动画效果
			}
		},
		computed: {

		},
		methods: {
			turn: function() {
				if (!this.open) {
					this.open = true;
				}
				this.isTrue = !this.isTrue;
			}
		}


	}
</script>

<style>
	.SwitchButton {

		/* background-color: white; */
		border-radius: 2.5rem;
		width: 3.5rem;
		height: 3rem;
		display: inline-block;
	}

	.backGround {
		position: absolute;
		height: 1rem;
		-webkit-background: aqua;
		background-color: aqua;
		background: #00FFFF;
		border-radius: 1rem;
		margin-top: 0.25rem;
		width: 2.5rem;
		/* z-index:1 ; */
	}

	.turn {
		/* position: absolute;
		border-radius: 50%;
		background-color: #DDA0DD;
			-webkit-background:red;
		background: red;
		height: 1.5rem;
		z-index: 1; */
		position: relative;
		top: -0.25rem;
		height: 1.5rem;
		border-radius: 50%;
		/* -webkit-background:red; */
		background-color: gold;
		/* background: #00FFFF; */
		border-radius: 1.5rem;
		margin-top: 0.25rem;
		width: 1.5rem;
		/* z-index:1 ; */

	}

	.turnGo {
		animation: switchButtonGo 1s;
		animation-fill-mode: forwards;
	}

	.turnBack {
		animation: switchButtonBack 1s;
		animation-fill-mode: forwards;
	}


	@keyframes switchButtonGo {
		0% {
			background: gold;
			left: 0px;
			top: -0.25rem;
		}
		100% {
			background: gold;
			left: 1rem;
			top: -0.25rem;
		}
	}

	@keyframes switchButtonBack {
		0% {
			background: gold;
			left: 1rem;
			top: -0.25rem;
		}
		100% {
			background: gold;
			left: 0rem;
			top: -0.25rem;
		}
	}

	@-moz-keyframes switchButton

	/* Firefox */
		{
		0% {
			background: red;
			left: 0px;
			top: 0px;
		}

		25% {
			background: yellow;
			left: 200px;
			top: 0px;
		}

		50% {
			background: blue;
			left: 200px;
			top: 200px;
		}

		75% {
			background: green;
			left: 0px;
			top: 200px;
		}

		100% {
			background: red;
			left: 0px;
			top: 0px;
		}
	}

	@-webkit-keyframes switchButton

	/* Safari and Chrome */
		{
		0% {
			background: red;
			left: 0px;
			top: 0px;
		}

		/* 	25%  {background:yellow; left:200px; top:0px;}
	50%  {background:blue; left:200px; top:200px;}
	75%  {background:green; left:0px; top:200px;} */
		100% {
			background: red;
			left: 2.5rem;
			top: 0px;
		}
	}

	@-o-keyframes switchButton

	/* Opera */
		{
		0% {
			background: red;
			left: 0px;
			top: 0px;
		}

		25% {
			background: yellow;
			left: 200px;
			top: 0px;
		}

		50% {
			background: blue;
			left: 200px;
			top: 200px;
		}

		75% {
			background: green;
			left: 0px;
			top: 200px;
		}

		100% {
			background: red;
			left: 0px;
			top: 0px;
		}
	}
</style>
