<template>
	<div class="ButtonI">
		<span style="display: inline-block;"> hello</span>
		<img src="../../assets/xiangyou.png" />
	</div>
</template>

<script>
	export default {

	}
</script>

<style scoped>
	.ButtonI {
		border-radius: 2.5rem;
		/* width: 100%; */
		height: 3.0rem;
		display: flex;
		/* justify-content: center; */
		text-align: center;
		align-items: center;
		background-color: red;
		box-shadow:0px 0px 10px #888888;

	}

	.ButtonI span {
		margin-left: 1.5rem;
		color: #FFFFFF;
	}

	.ButtonI img {
		float: right;
		height: 1rem;
		width: 2.5rem;
		margin-left: auto;
		margin-right: 1.5rem;
		text-align: center;
	}
</style>
