<template>
	<div>
		<span class="marginMLeft"> <strong>{{leftText}}</strong></span>
		<span class="marginMRigh"> {{rightText}}</span>

	</div>
</template>

<script>
	import "../../assets/public.css"
	export default {
		props: {
			leftText: {
				type:String,
				default:"leftText"
			},
			rightText:{
				type:String,
				default:"rightText"
			},
		}
	}
</script>

<style>
</style>
