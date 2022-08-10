<template>
  <div>
    <section class="carousel">
      <div class="carousel__inner" :style="`transform: translateX(${translate}px)`">
        <div v-for="(art, index) in arts" :key="art.name" :class="`carousel__item ${index === position - 1 ? 'active' : ''}`">
          <img @click="goTo(art.name)" :src="art.url" :alt="art.name">
          <h2>{{ art.name }}</h2>
        </div>
      </div>
    </section>
    <div class="container footer">
      <p>PHOTOGRAPHER</p>
      <div class="carousel-selector">
        <i @click="backward" class="fa-solid fa-chevron-left arrow"></i>
        <p>{{ position }}/3</p>
        <i @click="forward" class="fa-solid fa-chevron-right arrow"></i>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  transition: {
    name: 'page'
  },
  data() {
    return {
      translate: 950,
      position: 1,
      arts: [
        {
          name: 'Melanie',
          url: '/images/melanie.png'
        },
        {
          name: 'Prune',
          url: '/images/bruxells.png'
        },
        {
          name: 'Ange-Marie',
          url: '/images/problem.png'
        }
      ]
    }
  },
  watch: {
    translate() {
      switch(this.translate) {
        case 950:
          this.position = 1
          break;
        case 0:
          this.position = 2
          break;
        case -950:
          this.position = 3
          break;
      }
    }
  },
  methods: {
    forward() {
      if (this.translate === -950) return false;
      this.translate = this.translate - 950;
    },
    backward() {
      if (this.translate === 950) return false;
      this.translate = this.translate + 950;
    },
    goTo(name) {
      this.$router.push(`projects/${name}`);
    }
  }
}
</script>
