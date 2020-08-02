<template>
	<div class="Transcation mainFlexRow ">
		<img class="FlexOne img" src="../../assets/diqiu.png" />
		<span class="FlexSix"><strong>{{content}}</strong></span>
		<span class="FlexOne money" :style="{color:isRed==false?'red':'green'}">{{money}}</span>
	</div>
	<!-- <div v-else class="Transcation mainFlexRow ">
		<img  src="../../assets/AddwithcircleF.png"/>
		<span>Add New Card</span>
	</div> -->
</template>

<script>
	export default {
		props: {
			money: "",
			image: "",
			content: "",
			isAdd: false,
		},
		data: function() {
			return {

				isRed: true
			}
		},
		mounted() {
			console.log(this.image)
			if (this.money < 0) {
				this.isRed = false;
			}
		}

	}
</script>

<style scoped="scoped">
	.img{
		
	}
	.Transcation {
		width: 100%;
		background-color: #FFFFFF;
		height: 3.0rem;
	
	}

	.Transcation img {
		width: 2.5rem;
		height: 2.5rem;
		box-shadow:0px 0px 10px #000;
		margin-left: 0.625rem;
	}
	.Transcation .money{
		margin-right: 0.625rem;
	}
</style>
