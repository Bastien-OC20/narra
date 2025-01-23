<template>
  <header class="header container-fluid row">
    <nav class="nav col-12">
      <a class="nav-link" href="#home">
        <h1 class="title">NarraRealms</h1>
      </a>
      <ul class="nav">
        <li class="nav-item"><a class="nav-link" href="#home">Accueil</a></li>
        <li class="nav-item"><a class="nav-link" href="#about">À propos</a></li>
        <li class="nav-item"><a class="nav-link" href="#contact">Contact</a></li>
        <li class="nav-item">
          <a class="nav-link" href="/login"
            ><button class="btn btn-light">Connexion</button></a
          >
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/signup"
            ><button class="btn btn-light">Inscription</button></a
          >
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: "Navbar",
};
</script>

<style>
.header {
  color: white;
}

.title {
  font-size: 3rem;
  margin-right: 5px;
  text-shadow: 0 0 20px rgba(244, 248, 0, 0.911);
  color: white;
}

.nav-link {
  color: white;
  text-decoration: none;
}

.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
