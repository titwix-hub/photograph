<template>
    <section class="page__index">
        <nav>
            <div class="container">
                <div class="nav__left">
                    <nuxt-link to="/">About</nuxt-link>
                </div>
                <div class="nav__center">
                    <h1><nuxt-link to="/">Melanish</nuxt-link></h1>
                </div>
                <div class="nav__right">
                    <nuxt-link to="/">Contact</nuxt-link>
                </div>
            </div>
        </nav>
        <nuxt />
        <footer></footer>
    </section>
</template>

<script>
export default {
    name: 'default-layouts'
}
</script>