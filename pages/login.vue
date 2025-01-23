<template>
  <div class="col-12">
    <SecondNavBar />
    <div class="login-page">
      <h1>Connexion</h1>
      <form @submit.prevent="login">
        <div>
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="email" required />
        </div>
        <div>
          <label for="password">Mot de passe:</label>
          <input type="password" id="password" v-model="password" required />
        </div>
        <button type="submit">Se connecter</button>
      </form>
      <p class="mt-3">
        Pas Encore inscript ? Qu'est ce que tu attends ?
        <a class="nav-link" href="/signup">C'est par ici !</a>
      </p>
    </div>
  </div>
</template>

<script>
import SecondNavBar from "../components/SecondNavBar.vue";
export default {
  components: {
    SecondNavBar,
  },
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    login() {
      // Logique de connexion
      console.log("Email:", this.email);
      console.log("Mot de passe:", this.password);
    },
  },
};
</script>

<style>
.login-page {
  max-width: 400px;
  margin: 0 auto;
  padding: 1rem;
  text-align: center;
}

form div {
  margin-bottom: 1rem;
}

label {
  display: block;
  margin-bottom: 0.5rem;
}

input {
  width: 100%;
  padding: 0.5rem;
  box-sizing: border-box;
}

button {
  padding: 0.5rem 1rem;
  background-color: #007bff;
  color: white;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}
</style>
