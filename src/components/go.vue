/**
 * 围棋组件
 */
 <template>
    <canvas id="root"></canvas>
 </template>


 <script>
 export default {
     methods: {
         drawGrid(ctx) {
            //<!-- 绘制围棋棋盘 -->

            //1 计算棋盘的宽度，高度等于宽度
            var gridWidth = window.innerWidth;
            var gridHeight = gridWidth;

            //2 计算每个围棋格子的宽度
            var avergeWidth = (gridWidth) / 18;
            for(var j = 0; j <19; j++) {
                ctx.beginPath();
                ctx.moveTo(j * avergeWidth, 0);
                ctx.lineTo(j * avergeWidth, gridHeight);
                ctx.stroke();
            }
            for(var i = 0; i <19; i++) {
                ctx.beginPath();
                ctx.moveTo(0, i * avergeWidth);
                ctx.lineTo(gridWidth, i * avergeWidth);
                ctx.stroke();
            }
         }
     },
     mounted:function() {
         var ctx = document.getElementById("root").getContext("2d");
         this.drawGrid(ctx)
     }
 }
 </script>

 <style scoped>
     #root {
         width: 100%;
         height: 100%;
     }
 </style>