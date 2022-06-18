<template>
    <section class="container is-max-desktop">
        <!-- <div class="columns pb-6">
                <ThreeGames />
            </div> -->
        <div class="columns">
            <div class="column">
                <h1 class="title pb-4">
                    heartrift
                </h1>
                <p class="subtitle has-text-left">
                    A surreal adventure game where you play as a cat.<br><br>
                    The demo is now out on <a href="https://briakitten.itch.io/heartrift" target="_blank" rel="noopener noreferrer">itch.io!</a>
                    You can also check out the main website at <a href="https://heartrift.com" target="_blank" rel="noopener noreferrer">heartrift.com</a> for more info and updates.
                    </p>
            </div>
            <div class="column">
                <a class="image container is-256x256" href="https://briakitten.itch.io/" target="_blank" rel="noopener noreferrer">
                    <img src="~/assets/heartrift.png" >
                </a>
            </div>
        </div>
        <hr>
        <div class="columns">
            <div class="column">
                <h1 class="title pb-4">
                    Game Jams
                </h1>
                <p class="subtitle has-text-left">
                    Games that I have built in a few days (sometimes with a small team). The tools I use are Unity and GameMaker Studio 2. <br><br>

                    You can find a few of those games on my <a href="https://briakitten.itch.io/" target="_blank" rel="noopener noreferrer">itch.io.</a>
                </p>
            </div>
            <div class="column">
                <a class="image container is-256x256" href="https://briakitten.itch.io/" target="_blank" rel="noopener noreferrer">
                    <img src="~/assets/gamejams.png" >
                </a>
            </div>
        </div>
        <hr>
        <div class="columns">
            <div class="column">
                <h1 class="title pb-4">
                    Other Projects...
                </h1>
                <p class="subtitle has-text-left">
                    Outside of updates for my game (heartrift), I have other unnanounced projects in the works too.
                    <br><br>
                    Here is to looking to the future!
                </p>
            </div>
            <div class="column">
                <a class="image container is-256x256" href="https://briakitten.itch.io/heartrift" target="_blank" rel="noopener noreferrer">
                    <img src="~/assets/mystery.png">
                </a>
            </div>
        </div>
    </section>
</template>

<script>
import ThreeGames from '~/components/ThreeGames.vue';
export default {
    components: { ThreeGames }
}
</script>

<style>

</style>