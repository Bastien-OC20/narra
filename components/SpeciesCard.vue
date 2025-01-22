<template>
  <div class="card" :class="{ selected: isSelected }" @click="selectSpecies">
    <img :src="imageSrc" class="card-img-top" :alt="species">
    <div class="card-body">
      <h5 class="card-title">{{ species }}</h5>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    species: {
      type: String,
      required: true
    },
    imageSrc: {
      type: String,
      required: true
    },
    isSelected: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    selectSpecies() {
      this.$emit('select-species', this.species);
    }
  }
}
</script>

<style>
.card {
  width: 150px;
  margin: 1rem;
  cursor: pointer;
  transition: transform 0.2s;
}

.card:hover {
  transform: scale(1.05);
}

.card.selected {
  border: 2px solid #007BFF;
}

.card-img-top {
  width: 100%;
  height: auto;
}

.card-body {
  padding: 0.5rem;
}
</style>