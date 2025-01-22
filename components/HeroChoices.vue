<template>
  <div class="hero-choices col-8">
    <h2>Choix du Héros</h2>
    <ul>
      <li v-for="choice in choices" :key="choice" @click="selectChoice(choice)">
        {{ choice }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    choices: Array
  },
  methods: {
    selectChoice(choice) {
      this.$emit('select-choice', choice);
    }
  }
}
</script>

<style scoped>
.hero-choices {
  text-align: left;
  margin-bottom: 2rem;
}

.hero-choices ul {
  list-style-type: none;
  padding: 0;
background-color: #f0f0f0;
    border: 1px solid #ccc;
}

.hero-choices li {
  cursor: pointer;
  margin: 0.5rem 0;
  padding: 0.5rem;
  color: #000000;
}

.hero-choices li:hover {
  background-color: #e0e0e0;
}
</style>