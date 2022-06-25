<template>
    <section class="container px-6 mt-6 mb-6 is-max-desktop">
        <article class="content">
            <div class="card columns">
                <div class="column p-4 pl-5">
                    <nuxt-link to="blog">
                        <font-awesome-icon size="3x" :icon="['fas', 'chevron-left']"/>
                    </nuxt-link>
                </div>
                <div class="column is-11 p-4">
                    <h1 style="margin-bottom: 0px;">{{article.title}}</h1>
                    <span>{{article.date}}</span>
                </div>
            </div>
            <nuxt-content :document="article" />
        </article>
    </section>
</template>

<script>
export default {
    async asyncData({$content, params}) {
        const article = await $content('posts', params.slug).fetch();

        return { article };
    }
}

/*
<figure class="image container is-256x256">
    <img :src="require(`~/assets/${article.img}`)" />
</figure>

        */
</script>

<style>

</style>