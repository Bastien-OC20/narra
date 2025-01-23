<template>
  <div class="slider-container">
    <label for="morality">Moralité:</label>
    <div class="flex row justify-content-between">
      <p>Méchant</p>
      <p>Gentil</p>
      <input
        type="range"
        id="morality"
        v-model="morality"
        min="0"
        max="100"
        :style="{ background: sliderBackgroundColor }"
        @input="updateKarma"
      />
    </div>
    <span>{{ morality }}</span>
  </div>
</template>

<script>
export default {
  props: {
    morality: {
      type: Number,
      required: true,
    },
  },
  computed: {
    sliderBackgroundColor() {
      const green = Math.floor((this.morality / 100) * 255);
      const red = 255 - green;
      const purple = 75;
      return `linear-gradient(to right, rgb(${purple}, 0, ${red}), rgb(0, ${green}, 0))`;
    },
  },
  methods: {
    updateMorality(event) {
      this.$emit("update-morality", Number(event.target.value));
    },
  },
  watch: {
    morality(newVal) {
      this.$emit("update-morality", newVal);
    },
  },
};
</script>

<style>
.slider-container input[type="range"] {
  -webkit-appearance: none;
  appearance: none;
  width: 100%;
  height: 8px;
  border-radius: 5px;
  background: #fffefe;
  outline: none;
  opacity: 0.7;
  -webkit-transition: 0.2s;
  transition: opacity 0.2s;
}

.slider-container input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: #ffffff;
  cursor: pointer;
}

.slider-container input[type="range"]::-moz-range-thumb {
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: #ffffff;
  cursor: pointer;
}
</style>
