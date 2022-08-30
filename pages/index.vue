<template>
  <div class="_body">
    <Header />
  </div>
</template>

<script>
import About from '../components/About.vue'
import Header from '../components/Header.vue'
import Life from '../components/Life.vue'
import Service from '../components/Service.vue'
import Work from '../components/Work.vue'
export default {
  components: { Header, Service, About, Work, Life },
  name: 'IndexPage',
  setup() {
    return {
      titles: [Service, About, Work, Life],
    }
  },
}
</script>

<style lang="scss">
@import url(https://fonts.googleapis.com/css?family=Ubuntu:300,300italic,regular,italic,500,500italic,700,700italic);

// Var
$primaire: #eeeeee;
$font: 'Ubuntu', 'sans serif';

// Code
*,
*::before,
*::after {
  box-sizing: border-box;
  scroll-behavior: smooth;
}
._body {
  background-color: $primaire;
  font-family: $font;
}
</style>
