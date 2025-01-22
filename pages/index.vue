<template>
  <div class="Homepage">
    <Navbar />
    <section id="home">
      <div class="logo-container" @mousemove="handleMouseMove" @mouseleave="resetTransform">
        <h1><img src="../static/logo1.png" alt="Logo" class="logo" title="Bienvenue sur Narra Realms"></h1>
      </div>
      <p>Votre plateforme de narration interactive.</p>
      <button @click="goToPlay">Commencer</button>
    </section>

  </div>
</template>

<script>
import Navbar from '@/components/Navbar.vue';

export default {
  name: 'HomePage',
  components: {
    Navbar
  },
  methods: {
    goToSignup() {
      this.$router.push('/signup');
    },
    goToPlay() {
      this.$router.push('/hero');
    },
    handleMouseMove(event) {
      const logo = event.currentTarget.querySelector('.logo');
      const rect = logo.getBoundingClientRect();
      const x = event.clientX - rect.left; 
      const y = event.clientY - rect.top;  
      const centerX = rect.width / 2;
      const centerY = rect.height / 2;
      const rotateY = ((x - centerX) / centerX) * 15; 
      const rotateX = ((centerY - y) / centerY) * 15; 
      logo.style.transform = `rotateY(${rotateY}deg) rotateX(${rotateX}deg)`;
    },
    resetTransform(event) {
      const logo = event.currentTarget.querySelector('.logo');
      logo.style.transform = 'rotateY(0deg) rotateX(0deg)';
    }
  }
}
</script>

<style>


.Homepage {

  font-weight: 400;
  font-style: normal;
  font-size: 1.5rem;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 1rem;
  height : 100vh;
}

.logo-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 2rem;
  perspective: 1000px;
}

.logo {
  width: 50%;
  height: auto;
  transition: transform 0.1s ease-in-out;
}
</style>
