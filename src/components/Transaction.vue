<template>
	<div class="Transcation mainFlexRow " >
		<img class="FlexOne" :src="image" />
		<span class="FlexSix">{{content}}</span>
		<span class="FlexOne" :style="{color:isRed==false?'red':'green'}">{{money}}</span>
	</div>
</template>

<script>
	export default {
		props:{
			money:"",
			image:"",
			content:""
		},
		data: function () {
		   return {
		    money:"",
			image:"",
			content:"",
			isRed:true
		   }
		 },
		 mounted() {
		 	if(this.money<0){
				this.isRed=false;
			}
		 }
		
	}
</script>

<style>
	.Transcation{
		width: 100vw;
		height: 6.25rem;
	}
</style>
