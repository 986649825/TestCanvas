<template>
	<div class=" Current" ref="Current">
		<div class="marginMLeft" ref="title">{{title}}</div>
		<div class="MflexCenterAlign">

			<span class=" dashed" :style="{width: this.clientWidth}">

			</span>
		</div>
		<div class="marginMRigh" ref="money">{{money}}</div>
	</div>

</template>

<script>
	export default {
		props: {
			title: {
				type: String,
			},
			money: {
				type: String,
			}

		},

		data: function() {
			return {
				clientWidth: 0,
			}
		},
		mounted() {

			let that = this;

			that.$nextTick(function() {
				const Current = that.$refs.Current.clientWidth;
				const title = that.$refs.title.clientWidth;
				const money = that.$refs.money.clientWidth;
				that.clientWidth = Current - (title + money) + "px";

			});


		},
	}
</script>

<style>
	.Current {
		width: 100%;
		display: flex;
		justify-content: center;
		padding-left: 0.325rem;
		padding-right: 0.325rem;

	}

	.Current .title {
		margin-right: 10px;
		margin-top: 10px;
	}

	.Current .money {
		margin-left: 10px;
		margin-top: 10px;
	}

	.dashed {
		/* border: #2C3E50 0.0625rem; */
		/* border-bottom: #2C3E50 0.0125rem; */
		border: 1px solid black;
		borer-bottom: none;
		border-style: dashed;
		border-top: none;
		border-left: none;
		border-right: none;
		margin-left: 0.1625rem;
		padding-bottom: 1rem;



	}
</style>
