<template>
  <div class="card" :class="{ selected: isSelected }" @click="selectUnivers">
    <img :src="imageSrc" class="card-img-top" :alt="univers">
    <div class="card-body">
      <h5 class="card-title">{{ univers }}</h5>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    univers: {
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
    selectUnivers() {
      this.$emit('select-univers', this.univers);
    }
  }
}
</script>

<style >
.card {
    display: flex;
    justify-content: center;
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