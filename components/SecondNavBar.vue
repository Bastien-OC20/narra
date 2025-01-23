<template>
  <header class="header row">
    <nav class="nav col-12 row">
      <div class="logo-container">
        <img src="../static/logo1.png" alt="Logo" class="logo" />
      </div>
      <ul class="nav">
        <li class="nav-item">
          <button @click="goToHome" class="btn btn-light">Retour à l'accueil</button>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: "SecondNavbar",
  methods: {
    goToHome() {
      this.$router.push("/");
    },
  },
};
</script>

<style>
.header {
  color: white;
  padding: 1rem;
  display: flex;
  flex-direction: row;
}

.logo-container {
  display: flex;
  align-items: center;
  justify-content: left;
}

.logo {
  width: 20%;
  height: auto;
}

.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-item {
  list-style: none;
}
</style>
