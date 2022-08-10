<template>
    <section class="project">
        <div class="container">
            <div class="project__header">
                <h2 class="header__title">Melanie</h2>
                <div style="background-image: url('/images/Main-IMG.png')" class="header__img"></div>
            </div>

            <div class="project__info">
                <div>
                    <h3>Art director</h3>
                    <p>Geoff Levy</p>
                </div>
                <div>
                    <h3>Creative director</h3>
                    <p>Natailie Schneider</p>
                </div>
                <div>
                    <h3>Designer</h3>
                    <p>Em Design</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'Project',
    transition: {
        name: 'page'
    },
}
</script>