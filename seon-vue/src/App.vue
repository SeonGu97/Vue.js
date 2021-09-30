<template>
  <Nav />
  <Footer />
  <Container @v-update="update" />
</template>

<script>
import Nav from './components/Vue/Nav.vue';
import Footer from './components/Vue/Footer.vue';
import Container from './components/Vue/Container.vue';

export default {
  name: 'App',
  data() {
    return {
      
    }
  },
  components: {
    Nav,
    Footer,
    Container,
  },
  methods: {
    update() {
      console.log(this.$refs.cntr)
    },
    resize() {
      clearTimeout(this.timer);
      this.timer = setTimeout(() => {
        if(this.pc.matches) {
          console.log('pc');
        }
        
        if(this.tablet.matches) {
          console.log('tablet');
        }

        if(this.moblie.matches) {
          console.log('moblie');
        }
      }, this.dlray);
    }
  },
  mounted() {
    window.addEventListener('resize', this.resize);
    this.resize();
  },
  unmounted() {
    window.addEventListener('resize', this.resize);
  },
  setup() {
    const dlray = 300;
    const timer = null;
    const pc = window.matchMedia('(min-width: 1023px)');
    const tablet = window.matchMedia('(min-width:768px) and (max-width:1023px)');
    const moblie = window.matchMedia('(max-width:767px)');

    return {
      dlray,
      timer,
      pc,
      tablet,
      moblie,
    }
  }
}
</script>

<style>
/* reset css */
@import url("./components/CSS/Reset.css");

/* media query */
@import url("./components/CSS/Media.css");

/* css */
@import url("./components/CSS/Style.css");

/* google fonts */
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR&display=swap');
</style>
