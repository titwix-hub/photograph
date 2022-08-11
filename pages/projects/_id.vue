<template>
    <section class="project">
        <div class="scroll">{{ pos }}</div>
        <div class="container">
            <div class="project__header">
                <h2 class="header__title">Melanie</h2>
                <div id="header__img" style="background-image: url('/images/Main-IMG.png')" class="header__img"></div>
            </div>

            <div class="project__info">
                <transition name="slide">
                    <div v-show="info.showArtDirector">
                        <h3 class="t-poppins">Art director</h3>
                        <p class="t-nympha">Geoff Levy</p>
                    </div>
                </transition>
                <transition name="slide">
                    <div v-show="info.showCreativeDirector">
                        <h3 class="t-poppins">Creative director</h3>
                        <p class="t-nympha">Natailie Schneider</p>
                    </div>
                </transition>
                <transition name="slide">
                    <div v-show="info.showDesigner">
                        <h3 class="t-poppins">Designer</h3>
                        <p class="t-nympha">Em Design</p>
                    </div>
                </transition>
            </div>
        </div>
        <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
    </section>
</template>

<script>
export default {
    name: 'Project',
    transition: {
        name: 'page'
    },
    data() {
        return {
            pos: 0,
            info: {
                showArtDirector: false,
                showCreativeDirector: false,
                showDesigner: false
            }
        }
    },
    methods: {
        onScroll(e) {
            this.pos = window.top.scrollY
            /* or: e.target.documentElement.scrollTop */

            this.imgHeader(this.pos);
            this.infoArt(this.pos);
        },
        imgHeader(pos) {
            if (pos > 400) return false;

            const HEADER_IMG = document.getElementById('header__img');
            header__img.style.transform = `translateY(${pos/10}px)`;
        },
        infoArt(pos) {
            pos >= 400 ? this.info.showArtDirector = true : this.info.showArtDirector = false
            pos >= 420 ? this.info.showCreativeDirector = true : this.info.showCreativeDirector = false
            pos >= 440 ? this.info.showDesigner = true : this.info.showDesigner = false
        }
    },
    mounted() {
        window.addEventListener("scroll", this.onScroll)
    },
    beforeDestroy() {
        window.removeEventListener("scroll", this.onScroll)
    },
}
</script>