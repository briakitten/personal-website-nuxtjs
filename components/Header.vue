<template>
    <div>
        <div class="p-2"></div>
        <b-navbar class="container is-max-desktop" shadow=true>
            <template slot="brand">
                <b-navbar-item tag="nuxt-link" to="/" style="text-decoration:none;">>briakitten</b-navbar-item>
            </template>
            <template slot="end">
                <b-navbar-item tag="nuxt-link" to="/" style="text-decoration:none;">/____</b-navbar-item>
                <b-navbar-item tag="nuxt-link" to="/projects" style="text-decoration:none;">/projects</b-navbar-item>
                <b-navbar-item tag="nuxt-link" to="/blog" style="text-decoration:none;">/blog</b-navbar-item>
                <b-navbar-item tag="nuxt-link" to="/contact" style="text-decoration:none;">/contact</b-navbar-item>
            </template>
        </b-navbar>
    </div>
</template>

<script>
export default {
}
</script>

<style>

</style>