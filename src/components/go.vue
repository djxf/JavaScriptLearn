<template>
    <canvas id="canvas"></canvas>
</template>


 <script>
 const WIDTH = window.innerWidth - 30
 const HEIGHT = WIDTH
 const GRID_WIDTH = WIDTH / 18
 export default {
    methods: {
        drawGrid(ctx) {
            //<!-- 绘制围棋棋盘 -->

            //1 计算棋盘的宽度，高度等于宽度
            var gridWidth = WIDTH;
            var gridHeight = HEIGHT;

            //2 计算每个围棋格子的宽度
            var avergeWidth = (gridWidth) / 18;
            for(var j = 0; j < 19; j++) {
                ctx.beginPath();
                ctx.moveTo(j * avergeWidth, 0);
                ctx.lineTo(j * avergeWidth, gridHeight);
                ctx.stroke();
            }
            for(var i = 0; i < 19; i++) {
                ctx.beginPath();
                ctx.moveTo(0, i * avergeWidth);
                ctx.lineTo(gridWidth, i * avergeWidth);
                ctx.stroke();
            }
        },
        drawNinePoint(cxt) {
            var np = new Array(
            [GRID_WIDTH * 3,GRID_WIDTH * 3],[GRID_WIDTH * 3,GRID_WIDTH * 9],[GRID_WIDTH * 3,GRID_WIDTH * 15],
            [GRID_WIDTH * 9,GRID_WIDTH * 3],[GRID_WIDTH * 9,GRID_WIDTH * 9],[GRID_WIDTH * 9,GRID_WIDTH * 15],
            [GRID_WIDTH * 15,GRID_WIDTH * 3],[GRID_WIDTH * 15,GRID_WIDTH * 9],[GRID_WIDTH * 15,GRID_WIDTH * 15]);
	
            for (var i = 0; i < np.length; i++) {
                //circle
                cxt.beginPath();
                cxt.arc(np[i][0],np[i][1],3,0,2*Math.PI,false);
                cxt.fillStyle="black";
                cxt.fill();
            }
        }
    },
    mounted() {
        let canvas = document.getElementById("canvas")
        canvas.width = WIDTH;
        canvas.height = HEIGHT;
        var ctx = canvas.getContext("2d");
        this.drawGrid(ctx)
        this.drawNinePoint(ctx)
    }
 }
 </script>

 <style scoped>
 </style>