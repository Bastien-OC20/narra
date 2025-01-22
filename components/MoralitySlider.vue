<template>
    <div class="slider-container">
        <label for="morality">Moralité:</label>
        <div class="flex row justify-content-between">
            <p>Méchant</p>
            <p>Gentil</p>
            <input type="range" id="morality" v-model="morality" min="0" max="100">
        </div>
        <span>{{ morality }}</span>
    </div>
</template>

<script>
export default {
  props: {
    morality: {
      type: Number,
      required: true
    }
  },
  methods: {
    updateMorality(event) {
      this.$emit('update-morality', Number(event.target.value));
    }
  },
  watch: {
    morality(newVal) {
      this.$emit('update-morality', newVal);
    }
  }
}
</script>

<style >
.slider-container {
  margin-bottom: 1rem;
}

input[type="range"] {
  width: 100%;
}
</style>