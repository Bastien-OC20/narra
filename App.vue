<template>
    <div>
        <Navbar />
        <Nuxt />
    </div>
</template>

<script>
import Navbar from '@/components/Navbar.vue';
export default {
  name: 'App',
  components: {
    Navbar
  }
}
  
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Metal+Mania&display=swap');

html, body {
  font-family: 'Metal Mania', cursive;
}
</style>