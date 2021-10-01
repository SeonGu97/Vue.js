<template>
  <Nav ref="nav" />
  <Side @click="side" ref="side" />
  <Container @v-update="update" ref="cntr" />
  <Footer />
</template>

<script>
import Nav from './components/Vue/Nav.vue';
import Side from './components/Vue/Side.vue';
import Container from './components/Vue/Container.vue';
import Footer from './components/Vue/Footer.vue';

export default {
  name: 'App',
  data() {
    return {

    }
  },
  components: {
    Nav,
    Side,
    Container,
    Footer,
  },
  methods: {
    update() {
        if(this.pc.matches) {
          this.$refs.nav.$el.classList.toggle('hide');
          this.$refs.cntr.$el.classList.toggle('expansion');
        }

        if(this.tablet.matches) {
          this.$refs.nav.$el.classList.toggle('clone-hide');
          this.$refs.cntr.$el.classList.toggle('clone-expansion');

          this.$refs.side.$el.classList.add('show');
        }

        if(this.moblie.matches) {
          this.$refs.nav.$el.classList.toggle('clone-hide');
          this.$refs.cntr.$el.classList.toggle('clone-expansion');

          this.$refs.side.$el.classList.add('show');
        }
    },
    resize() {
      clearTimeout(this.timer);
      this.timer = setTimeout(() => {
        if(this.pc.matches) {
          if(this.$refs.side.$el.classList.contains('show')) {
            this.$refs.nav.$el.classList.remove('clone-hide');
            this.$refs.cntr.$el.classList.remove('clone-expansion');
            this.$refs.side.$el.classList.remove('show');
          }
        }
        
        if(this.tablet.matches) {
          this.$refs.nav.$el.classList.remove('hide');
          this.$refs.cntr.$el.classList.remove('expansion');
        }

        if(this.moblie.matches) {
          this.$refs.nav.$el.classList.remove('hide');
          this.$refs.cntr.$el.classList.remove('expansion');
        }
      }, this.dlray);
    },
    side() {
      this.$refs.side.$el.classList.remove('show');
      this.$refs.nav.$el.classList.remove('clone-hide');
      this.$refs.cntr.$el.classList.remove('clone-expansion');
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
