<template>
	<div  v-if="{isAdd}" class="card ">
		<span class="FlexOne" ><strong>$1212</strong></span>
		<div class="FlexOne">
			{{money}}
		</div>
	    <div class="FlexOne " style="display: flex;flex-direction: row;">
			
			<div  style="flex:1;display: flex;color: #F0F8FF;">
				{{name}}
			</div>
			<div    class="switch" >
				<switch-button ></switch-button>
			</div>
			
		</div>
	
		
	</div>
	
	<div v-else class="card mainFlexColumn ">
		<img  src="../../assets/AddwithcircleF.png"/>
		<span class="marginMTop" style="font-size: 0.75rem;">Add New Card</span>
	</div>
</template>

<script>
	import SwitchButton from "./SwitchButton.vue"
	export default{
		props:{
			isAdd:false,
			money:"",
			name:"",
		
		},
		components:{
			"switch-button":SwitchButton
		}
	}
</script>

<style>
	.card{
		height: 7.25rem;
		border-radius:0.55rem;
		/* background-color: #FFFFFF; */
		width: 100%;
		display: flex;
		flex-direction: column;
		background-color: red;
		padding-left: 0.625rem;
		padding-top: 0.625rem;
		box-shadow:0px 0px 10px #888888;
	
	}
	.card span{
		color: white;
		margin-top: 0.625rem;
		
	}
	.card .switch{
		  display: -webkit-flex; 
		 
		display: flex;
		
		flex-direction: row-reverse;
		
	}
	
</style>
