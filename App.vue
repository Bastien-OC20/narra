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

html, body {
  font-family: 'Metal Mania', cursive;
}
</style>