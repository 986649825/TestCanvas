<template>
	<div id="app">
		<!-- <img alt="Vue logo" src="./assets/logo.png"> -->
		<!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
		<!-- <CirclePoccess></CirclePoccess>
	 <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
		<!-- <ButtonI></ButtonI> -->
		<!-- <Transaction content="hello"money="-12" ></Transaction> -->
		<!-- <SeveviceItem style="width: 100px;height: 100px;"></SeveviceItem> -->
		<!-- <Card></Card> -->
		<div class="FlexThree AppMain ">
			<span class="marginMLeft"><strong>Card</strong></span>
			<div class=" cardItem">
				<div style="flex:1;padding: 10px;" v-for="(card,index) in cardList">
					<Card></Card>
				</div>





			</div>
			<div class="leftMain FlexTwo">
				<div class="FlexOne ServiceM" style="background-color: antiquewhite;">
    <div class="ServiceTitle">
		<span class="marginMLeft" style="float: left;"><strong>MainService</strong></span>
		<span class="marginMRigh" style="float: right;text-overflow: ellipsis">hello</span>
	</div>
	 <!-- sevi -->
	    <div  class="mainFlexRow ServiceMItem" style="position: relative;">
			<ServiceItem style="flex:1;"></ServiceItem>
			<ServiceItem style="flex:1;height:expression(this.clientWidth)"></ServiceItem>
		</div>
		
		<div  class="mainFlexRow">
			<ServiceItem style="flex:1; height:expression(this.clientWidth)"></ServiceItem>
			<ServiceItem style="flex:1;height:expression(this.clientWidth)"></ServiceItem>
		</div>
		<div  class="mainFlexRow">
			<ServiceItem style="flex:1;height:expression(this.clientWidth)"></ServiceItem>
			<ServiceItem style="flex:1;height:expression(this.clientWidth)"></ServiceItem>
		</div>
	
				</div>
				<div class="FlexTwo" style="background-color: #2C3E50;height: 100%; position: relative;">
                  
				</div>
			</div>
		</div>
		
		
		<!--  sidebar-->
		<div class="FlexOne sidebar " style="">
           <CirclePoccess></CirclePoccess>
		   <div style="width: 100%;">
			   <span class="marginMLeft" > Transaction</span>
			   <span class="marginMRigh" > tody</span>
			   
		   </div>
		 
		 
		  <Transaction  v-for="(Transaction,index) in TransactionList" style="margin-top:0.625rem" image="../../assets/diqiu.png" content="hello"money="-12"  ></Transaction>
		   <ButtonI style="margin-top: 0.625rem;margin-left: 0.625rem;margin-right: 0.625rem;"></ButtonI> 
		</div>
	</div>
</template>

<script>
	import "./assets/public.css"
	import CirclePoccess from './components/app/CirclePoccessItem.vue'
	import ServiceItem from './components/app/ServiceItem.vue'
	import ButtonI from "./components/app/ButtonI.vue"
	import Transaction from "./components/app/Transaction.vue"
	import Card from "./components/app/Card.vue"
	export default {
		name: 'app',
		components: {
		
			CirclePoccess,
			ServiceItem,
			ButtonI,
			Transaction,
			Card
		},
		data: function() {
			return {
				cardList: [1, 2, 3],
				serviceItemHeight:0,
				TransactionList:[1,2,3],

			}
		},
		mounted() {
		
		},
		methods:function(){
			
		}
	}
</script>

<style>
	#app {
		font-family: 'Avenir', Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		/* text-align: center; */
		color: #2c3e50;
		margin-top: 60px;
		background-color: lightgrey;
		height: 100vh;
		display: flex;
		flex-direction: row;
	}
      
	.AppMain {
		display: flex;
		flex-direction: column;

	}

	.sidebar {
		background-color: beige;
		border-radius: 0.625rem;
		text-align: center;
		/* display: flex; */
		/* align-items: center; */
		
	}
	
     
	.cardItem {
		display: flex;
		flex-direction: row;
		-webkit-justify-content: space-around;
		/* Safari 6.1+ */
		display: flex;
		justify-content: space-around;
		

	}
	/**
	 * sevice 和 折线图
	 */
	.leftMain{
		display: flex;
	   
		
	}
	
	.ServiceM{
		
		border-radius: 0.55rem;
		
	}
	.ServiceTitle{
		width: 100%;
		overflow: hidden;
		
	}
	
    .ServiceMItem{
		justify-content: space-around;
		-webkit-justify-content: space-around;
	}
	.card Card {}
</style>
