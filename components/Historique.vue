<template>
  <div class="historique col-4">
    <h2>Historique</h2>
    <ul>
      <li v-for="(entry, index) in historique" :key="index">
        {{ entry }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Historique',
  props: {
    historique: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
.historique {
  padding: 1rem;
  background-color: #f9f9f9;
  border: 1px solid #ddd;
  border-radius: 4px;
  color: #000000;
}
.historique h2 {
  margin-bottom: 0.5rem;
}
.historique ul {
  list-style-type: none;
  padding: 0;
}
.historique li {
  margin-bottom: 0.5rem;
}
</style>