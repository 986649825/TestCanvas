<template>
	<div class="Service mainFlexColumn" ref="companyStyle">
		<img src="../../assets/logo.png" />
		<span><strong style="margin-bottom: 0.625rem;">hello</strong></span>
	</div>
</template>

<script>
	export default {
		data: function() {
			return {
				clientWidth: 0,
				screenWidth: 0,
				screenHeight: 0,

			}
		},
		mounted() {
			let that = this;
			that.$nextTick(function() {
				const eWidth = that.$refs.companyStyle.clientWidth;
				console.log(eWidth);
				that.clientWidth = eWidth + "px";
			});
			window.onresize = () => {
				that.$nextTick(function() {
					const eWidth = that.$refs.companyStyle.clientWidth;
					console.log(eWidth);
					that.clientWidth = eWidth + "px";
				});
			}
			this.screenWidth = document.body.clientWidth;
			this.screenHeight = document.body.clientHeight;
			window.onresize = () => {
				return (() => {
					this.screenWidth = document.body.clientWidth;
					this.screenHeight = document.body.clientHeight;
					console.log(this.screenWidth)
				})();

			};


		},
		computed: {
			getclientWidth: function() {
				const eWidth = that.$refs.companyStyle.clientWidth;
				console.log(eWidth) + "px";
				// that.clientWidth=eWidth+"px";
				return eWidth

			}
		},
		watch: {

		}
	}
</script>

<style>
	.Service {
		margin: 0.125rem ;
		background-color: white;
		border-radius: 10%;
		padding: 1% 0 1% 0;
		height: 6.5rem;
		width: 1.5rem;
		/* box-shadow: 10px 10px 5px #888888; */
		/* box-shadow:inset 2px 2px 3px #000; */
		box-shadow: 0px 0px 10px #888888;
		border: 0.0625rem solid #888888;
	}

	.Service img {
		width: 40px;
		height: 40px;
		margin-top: 0.625rem;
	}
</style>
