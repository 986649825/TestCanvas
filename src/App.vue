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
		<div class="FlexTwo AppMain FlexOne">
			<span>Card</span>
			<div class=" cardItem">
				<div style="flex:1;padding: 10px;" v-for="(card,index) in cardList">
					<Card></Card>
				</div>





			</div>
			<div class="mainFlexRow FlexTwo">
				<div class="FlexOne" style="background-color: antiquewhite;height: 100%;">
    hel
				</div>
				<div class="FlexTwo" style="background-color: #2C3E50;height: 100%;">
hell
				</div>
			</div>
		</div>
		<div class="FlexOne sidebar">

		</div>
	</div>
</template>

<script>
	import "./assets/public.css"
	import HelloWorld from './components/app/HelloWorld.vue'
	import CirclePoccess from './components/app/CirclePoccessItem.vue'
	import ServiceItem from './components/app/ServiceItem.vue'
	import ButtonI from "./components/app/ButtonI.vue"
	import Transaction from "./components/app/Transaction.vue"
	import Card from "./components/app/Card.vue"
	export default {
		name: 'app',
		components: {
			HelloWorld,
			CirclePoccess,
			ServiceItem,
			ButtonI,
			Transaction,
			Card
		},
		data: function() {
			return {
				cardList: [1, 2, 3],

			}
		}
	}
</script>

<style>
	#app {
		font-family: 'Avenir', Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
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
	}

	.cardItem {
		display: flex;
		flex-direction: row;
		-webkit-justify-content: space-around;
		/* Safari 6.1+ */
		display: flex;
		justify-content: space-around;

	}

	.card Card {}
</style>
