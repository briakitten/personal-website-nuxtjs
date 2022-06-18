<template>
    <section class="container is-max-desktop">
        <div class="content">
            <h3 class="posts is-text-center">
                Latest Posts&nbsp;&nbsp;&nbsp;__φ(．．)
            </h3>

            <div class="card m-6 p-4" v-for="article of articles" :key="article.name">
                <nuxt-link style="text-decoration:none;" :to="{name: 'slug', params: {slug: article.slug} }">
                    <div class="columns pl-3">
                        <div class="column">
                            <h1 style="margin-bottom: 0px;">{{article.title}}</h1>
                            <span>{{article.date}}</span>
                            <p class="pt-3">{{article.description}}</p>
                        </div>
                    </div>
                </nuxt-link>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    async asyncData({ $content, params} ){
        const articles = await $content('posts', params.slug)
            .only(['title', 'description', 'img', 'slug', 'date', 'index'])
            .sortBy('index', 'date')
            .fetch();

        return { articles };
    },

    methods: {
        formatDate(date) {
            // format the date to be displayed in a readable format
            return new Date(date).toLocaleDateString('en', {
            year: 'numeric',
            month: 'long',
            day: 'numeric',
            })
        },
    }
}

//<img class="card-content column is-4" :src="require(`~/assets/${article.img}`)" />
</script>

<style>

</style>