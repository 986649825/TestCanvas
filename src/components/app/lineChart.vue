<template>
	<canvas id="chart" width="100" height="100"> 你的浏览器不支持HTML5 canvas </canvas>
</template>

<script>
	let canvas;
	let ctx;
	let cMargin;
	let cHeight;
	let cWidth;
	let originX;
	let originY;
	let cSpace;

	export default {
		props: {
			width: {
				type: Number,
				default: 480
			},
			height: {
				type: Number,
				default: 320
			}
		},
		data: function() {
			return {
				chartList: [
					["01", 50],
					["02", 60],
					["03", 100],
					["04", 200],
					["05", 350],
					["06", 600]
				],

			}
		},
		mounted() {
			this.initCanvas();
			// 当调整窗口大小时重绘canvas
			window.onresize = () => {
				this.initCanvas()
			}
		},
		methods: {
			initCanvas() {
				console.log("初始化canvas")
				canvas = document.getElementById('chart');
				ctx = canvas.getContext('2d');

				canvas.width = this.width;
				canvas.height = this.height;
				// this.drawCircleByStoke()
				ctx.font = "12px Arial";
				ctx.lineWidth = 1;
				ctx.fillStyle = "#566a80";
				ctx.strokeStyle = "#566a80";
				ctx.strokeStyle = "#E0E0E0";
				cMargin = 35;
				cSpace = 50;
				cHeight = canvas.height - cMargin - cSpace;
				cWidth = canvas.width - cMargin - cSpace;
				originX = cMargin + cSpace;
				originY = cMargin + cHeight;

				// this.drawLineX();
				// this.drawLineY();
				this.drawLine(originX, originY, originX, cMargin);
				// x轴
				this.drawLine(originX, originY, originX + cWidth, originY);
				this.drawMarkers();
			},
			
		
			drawLine(x, y, X, Y) {
				ctx.beginPath();
				ctx.moveTo(x, y)
				ctx.lineTo(X, Y);
				ctx.stroke();
				ctx.closePath();
			},
			drawMarkers() {
				// 折线图信息
				var dataArr = this.chartList;
				//根据数据的多少来计算的每个点距离
				var tobalDots = dataArr.length;
				var dotSpace = parseInt(cWidth / tobalDots);
				
				var maxValue = 0;
				for (var i = 0; i < dataArr.length; i++) {
					var dotVal = parseInt(dataArr[i][1]);
					if (dotVal > maxValue) {
						maxValue = dotVal;
					}
				}

				maxValue += 50;
				var totalYNomber = 10;

				// 绘制 y 轴 及中间横线
				var oneVal = parseInt(maxValue / totalYNomber);
				ctx.textAlign = "right";
				for (var i = 0; i <= totalYNomber; i++) {
					var markerVal = i * oneVal;
					var xMarker = originX - 5;
					var yMarker = parseInt(cHeight * (1 - markerVal / maxValue)) + cMargin;

					ctx.fillText(markerVal, xMarker, yMarker + 3, cSpace); // 文字
					if (i > 0) {
						this.drawLine(originX + 2, yMarker, originX + cWidth, yMarker);
					}
				}
				var oneVal = parseInt(maxValue / totalYNomber);

				// 绘制 x 轴 及中间竖线
				ctx.textAlign = "center";
				for (var i = 0; i < tobalDots; i++) {
					var markerVal = dataArr[i][0];
					var xMarker = originX + i * dotSpace;
					var yMarker = originY + 30;
					ctx.fillText(markerVal, xMarker, yMarker, cSpace); // 文字
					if (i > 0) {
						this.drawLine(xMarker, originY - 2, xMarker, cMargin);
					}
				}
				// 绘制标题 y
				ctx.save();
				ctx.rotate(-Math.PI / 2);
				ctx.fillText("访问量", -canvas.height / 2, cSpace - 10);
				ctx.restore();
				// 绘制标题 x
				ctx.fillText("月份", originX + cWidth / 2, originY + cSpace / 2 + 20);
			}


		}

	}
</script>

<style>




</style>
