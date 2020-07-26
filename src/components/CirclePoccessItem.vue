<template>
	<canvas id="canvas"  width="100" height="100" >
	Your browser does not support the canvas element.
	</canvas>
</template>

<script>
	let canvas;
	let ctx;
	export default {
		
	 data: function () {
	    return {
	      x: 100,
		  y:100,
		  radius:50
	    }
	  },
	  mounted() {
	    this.initCanvas()
	    // 当调整窗口大小时重绘canvas
	    window.onresize = () => {
	      this.initCanvas()
	    }
	  },
	  methods: {
	    initCanvas() {
	      console.log("初始化canvas")
	      canvas = document.getElementById('canvas');
	      ctx = canvas.getContext('2d');
	      canvas.width = "200";
	      canvas.height = "200";
	      this.drawCircle()
	    },
	    drawSmile() {
	      ctx.beginPath();
	      ctx.arc(75, 75, 50, 0, Math.PI * 2, true); // 绘制
	      ctx.moveTo(110, 75);
	      ctx.arc(75, 75, 35, 0, Math.PI, false); // 口(顺时针)
	      ctx.moveTo(65, 65);
	      ctx.arc(60, 65, 5, 0, Math.PI * 2, true); // 左眼
	      ctx.moveTo(95, 65);
	      ctx.arc(90, 65, 5, 0, Math.PI * 2, true); // 右眼
	      ctx.stroke();
	    },
		drawCircle(){
			// document.getElemntById("canvas").setAttribute("width","200px")
			// document.getElemntById("canvas").setAttribute("height","200px")
			//   var x=48;
		
			// 将绘图区域清空,如果是第一次在这个画布上画图,画布上没有东西,这步就不需要了
			    ctx.clearRect(0, 0, 48, 48);
			     
			// ***开始画一个灰色的圆
			    ctx.beginPath();
			        // 坐标移动到圆心
			    ctx.moveTo(this.x, this.y);
			        // 画圆,圆心是24,24,半径24,从角度0开始,画到2PI结束,最后一个参数是方向顺时针还是逆时针
			    ctx.arc(this.x,this.y, this.radius, 0, Math.PI * 2, false);
			    ctx.closePath();
			        // 填充颜色
			    ctx.fillStyle = '#ddd';
			    ctx.fill();
				
				// 画进度
				ctx.beginPath();
				    // 画扇形的时候这步很重要,画笔不在圆心画出来的不是扇形
				ctx.moveTo(this.x, this.y);
				    // 跟上面的圆唯一的区别在这里,不画满圆,画个扇形
				ctx.arc(this.x,this.y, this.radius, 0, Math.PI * 2 * 25 / 100, false);
				ctx.closePath();
				ctx.fillStyle = '#e74c3c';
				ctx.fill();
				
				
				// 画进度
				ctx.beginPath();
				    // 画扇形的时候这步很重要,画笔不在圆心画出来的不是扇形
				ctx.moveTo(this.x, this.y);
				    // 跟上面的圆唯一的区别在这里,不画满圆,画个扇形
				ctx.arc(this.x, this.y, this.radius, Math.PI * 2 * 25 / 100, Math.PI * 2 * 50/ 100, false);
				ctx.closePath();
				ctx.fillStyle = 'green';
				ctx.fill();
				
				// 画进度
				ctx.beginPath();
				    // 画扇形的时候这步很重要,画笔不在圆心画出来的不是扇形
				ctx.moveTo(this.x,this.y);
				    // 跟上面的圆唯一的区别在这里,不画满圆,画个扇形
				ctx.arc(this.x, this.y, this.radius, Math.PI * 2 * 50/ 100, Math.PI * 2 * 75/ 100, false);
				ctx.closePath();
				ctx.fillStyle = 'gold';
				ctx.fill();
				console.log(process);
				
				
				// 画内部空白
				ctx.beginPath();
				ctx.moveTo(this.x, this.y);
				ctx.arc(this.x, this.y, this.radius-10, 0, Math.PI * 2, true);
				ctx.closePath();
				ctx.fillStyle = 'rgba(255,255,255,1)';
				ctx.fill();
				
				
				
				//在中间写字
				ctx.font = "bold 9pt Arial";
				ctx.fillStyle = '#e74c3c';
				ctx.textAlign = 'center';
				ctx.textBaseline = 'middle';
				ctx.moveTo(this.x, this.y);
				ctx.fillText("51%", this.x, this.y-8);
				ctx.fillText("51%", this.x, this.y+8);
				// ctx.font = "bold 9pt Arial";
				// ctx.fillStyle = '#e74c3c';
				// ctx.textAlign = 'center';
				// ctx.textBaseline = 'middle';
				// ctx.moveTo(24, 70);
				// ctx.fillText("$199", 24, 24);
		}
		
	  }
	}
</script>

<style>
	/* canvas {
	  width: 20rem;
	  height: 20rem;
	} */
</style>
