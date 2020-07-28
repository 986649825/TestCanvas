<template>
	<div id="app">
		<div class="main">
			<div class="FlexThree AppMain ">
				<!-- <span class="marginMLeft"><strong>Card</strong></span> -->
				<MTitle></MTitle>
				<div class=" cardItem">
					<div style="flex:1;padding: 10px;" v-for="(card,index) in cardList">
						<Card></Card>
					</div>
				</div>
				<div class="leftMain FlexTwo">
					<div class="FlexOne ServiceM ">
						<div class="ServiceTitle">
							<span class="marginMLeft" style="float: left;"><strong>MainService</strong></span>
							<span class="marginMRigh" style="float: right;text-overflow: ellipsis">hello</span>
						</div>


						<!-- sevice-->
						<div class="mainFlexRow ServiceMItem" style="position: relative;">
							<ServiceItem style="flex:1;"></ServiceItem>
							<ServiceItem style="flex:1;"></ServiceItem>
						</div>

						<div class="mainFlexRow">
							<ServiceItem style="flex:1;"></ServiceItem>
							<ServiceItem style="flex:1;"></ServiceItem>
						</div>
						<div class="mainFlexRow">
							<ServiceItem style="flex:1;"></ServiceItem>
							<ServiceItem style="flex:1;"></ServiceItem>
						</div>

					</div>
					
					
					<div class=" ServiceRight FlexTwo " style="background-color:#FFFFFF;height: 100%; position: relative;">
						<MTitle></MTitle>
						<Current :title="123" :money="'hell'" ></Current>
					</div>
				</div>
			</div>


			<!--  sidebar-->
			<div class="FlexOne sidebar " style="">
				<MTitle></MTitle>
				<CirclePoccess></CirclePoccess>


				<MTitle></MTitle>


				<Transaction v-for="(Transaction,index) in TransactionList" style="margin-top:0.625rem" image="../../assets/diqiu.png"
				 content="hello" money="-12"></Transaction>
				<ButtonI style="margin-top: 0.625rem;margin-left: 0.625rem;margin-right: 0.625rem;"></ButtonI>
			
			</div>
			
			
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
	import MTitle from "./components/app/MTiltle.vue"
	import Current from "./components/app/Current.vue"
	export default {
		name: 'app',
		components: {

			CirclePoccess,
			ServiceItem,
			ButtonI,
			Transaction,
			Card,
			MTitle,
			Current
		},
		data: function() {
			return {
				cardList: [1, 2, 3],
				serviceItemHeight: 0,
				TransactionList: [1, 2, 3],
				CurrentList:[
					{title:'中国',money:"$1231"},
					{title:'美国',money:"$1231"},
					{title:'日本',money:"$1231"},
				]

			}
		},
		mounted() {

		},
		methods: function() {

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
		/* margin-top: 60px; */
		background-color: pink;
		height: 100vh;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		min-height: 64rem;
		min-width: 64rem;
		

	}

	.main {
		width: 80%;
		height: 60%;
		display: flex;
		background-color: white;
		border-radius: 1.5rem;
		
	}

	.AppMain {
		display: flex;
		flex-direction: column;
		margin-left: 1.25rem;
		margin-bottom: 1.25rem;

	}

	.sidebar {
		background-color: white;
		border-radius: 1rem;
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
	.leftMain {
		display: flex;


	}

	.ServiceM {

		border-radius: 0.55rem;
		background-color: aliceblue;
		


	}

	.ServiceTitle {
		width: 100%;
		overflow: hidden;

	}
	

	.ServiceMItem {
		justify-content: space-around;
		-webkit-justify-content: space-around;
	}
	.ServiceRight{
		display: flex;
		flex-direction: column;
	}

	.card Card {}
</style>
