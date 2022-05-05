<script>
import Header from './components/Header.vue';
import IntroSection from './components/IntroSection.vue';

export default {
  components: {
    Header,
    IntroSection
  }
}
</script>

<template>
  <Header />

  <main>
    <IntroSection />
  </main>
</template>

<style>
@import './assets/base.css';
</style>
