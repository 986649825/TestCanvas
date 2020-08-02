<template>
	<div class="mainFlexRow FlexSpace">
		<slot></slot>
	</div>
</template>

<script>
	export default{
		props:{
			orientation:"",
			
		}
	}
</script>

<style>
	
	.FlexSpace {
		justify-content: space-around;
		-webkit-justify-content: space-around;
	}
</style>
