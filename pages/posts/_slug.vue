<template>
    <article class="content">
        <figure class="image container is-256x256">
            <img :src="require(`~/assets/${article.img}`)" />
        </figure>
        <div class="card columns">
            <div class="column p-3 pl-5">
                <h1 style="margin-bottom: 0px;">{{article.title}}</h1>
                <span>{{article.date}}</span>
            </div>
        </div>
        <nuxt-content :document="article" />
    </article>
</template>

<script>
export default {
    async asyncData({$content, params}) {
        const article = await $content('posts', params.slug).fetch();

        return { article };
    }
}
</script>

<style>

</style>