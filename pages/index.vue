<template>
    <div>
        <section class="container  is-max-desktop">
            <canvas id="myCanvas" width="960" height="760" />
            <div class="columns px-6 mt-6 mb-6 pt-5 pb-5">
                <div class="column is-half">
                    <h1 class="title is-1 mb-6">
                        Hello, I'm Bria!
                    </h1>
                    <p class="subtitle is-5">
                        I am a game programmer with experience in web development. I love science, space, VR...
                        and weird niche indie games.<br/><br />Click on the TV to find what I've been working on.
                    </p>
                    <br><br>
                    <div class="columns">
                        <!-- <div class="column">ヾ｜￣ー￣｜ﾉ</div>
                        <div class="column">●__●</div> -->
                    </div>
                </div>
                <div class="column">
                    <a class="image container is-256x256" href="https://heartrift.com/" target="_blank" rel="noopener noreferrer">
                        <img src="~/assets/tv.png" >
                    </a></div>
            </div>
        </section>

    </div>
</template>

<script>
export default {
    name: 'IndexPage',
    data: {
        canvas: null,
        squares: [[]],
        translateY: 0
    },
    methods: {
        drawSquares(ctx, squareWidth, offset) {
            ctx.fillStyle = "#d0c1fd";
            for (let i = 0; i < this.squares.length; i++) {
                for (let j = 0; j < this.squares[i].length; j++) {
                    // const isFilled = (i % 2) - (j % 2);
                    const isFilled = this.squares[i][j];
                    if (isFilled) ctx.fillRect(i * squareWidth, j * squareWidth + offset, squareWidth, squareWidth);
                }
            }
        },
        draw() {
            /** @type {CanvasRenderingContext2D}*/
            let ctx = this.canvas;

            const c = document.getElementById("myCanvas");
            c.width = c.height * (c.clientWidth / c.clientHeight);
            const squareWidth = 64 * (c.width / 960);
            const squareTotalHeight = (squareWidth * this.squares[0].length);

            this.translateY -= 2;
            if (this.translateY <= -squareTotalHeight) this.translateY += squareTotalHeight;
            this.drawSquares(ctx, squareWidth, this.translateY)
            this.drawSquares(ctx, squareWidth, this.translateY + squareTotalHeight)
        },
        loop() {
            this.draw();

            requestAnimationFrame(this.loop);
        }
    },
    mounted() {
        var c = document.getElementById("myCanvas");
        this.canvas = c.getContext('2d');

        this.squares = [
            [ 0, 1, 0, 0, 0, 1, 1, 1, 0, 0, 1, 0, 0, 0, 0],
            [ 1, 0, 0, 1, 1, 0, 1, 0, 0, 0, 0, 1, 0, 0, 1],
            [ 0, 0, 1, 0, 0, 1, 0, 0, 0, 1, 1, 0, 0, 1, 1],
            [ 0, 0, 0, 1, 0, 0, 1, 1, 0, 0, 0, 0, 0, 1, 1],
            [ 0, 1, 1, 0, 0, 1, 0, 0, 0, 0, 0, 1, 0, 0, 0],
            [ 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0],
            [ 1, 0, 0, 0, 1, 0, 0, 1, 0, 0, 0, 0, 1, 0, 1],
            [ 0, 0, 0, 1, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 0],
            [ 0, 1, 0, 0, 1, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0],
            [ 0, 0, 1, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0, 1, 0],
            [ 1, 0, 0, 0, 1, 0, 1, 0, 0, 0, 0, 1, 0, 1, 1],
            [ 0, 0, 1, 1, 0, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0],
            [ 0, 1, 1, 0, 0, 1, 0, 0, 0, 0, 0, 1, 0, 0, 0],
            [ 0, 0, 0, 1, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 0],
            [ 0, 0, 1, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0, 1, 0]
        ]
        this.translateY = 0;

        this.loop();
    },
}
</script>

<style>
#myCanvas {
    display: inline-block;
    color:aliceblue;
    position: absolute;
    top: -48px;
    z-index: -100;
    width: 960px;
    height: 150%;
    resize:inherit;
}
</style>