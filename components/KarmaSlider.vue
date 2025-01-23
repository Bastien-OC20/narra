<template>
  <div class="slider-container">
    <label for="karma">Karma:</label>
    <div class="flex row justify-content-between">
      <p>Chaotique</p>
      <p>Héroïque</p>
      <input
        type="range"
        id="karma"
        v-model="karma"
        min="0"
        max="100"
        :style="{ background: sliderBackgroundColor }"
        @input="updateKarma"
      />
    </div>
    <span>{{ karma }}</span>
  </div>
</template>

<script>
export default {
  props: {
    karma: {
      type: Number,
      required: true,
    },
  },
  computed: {
    sliderBackgroundColor() {
      const green = Math.floor((this.karma / 100) * 165);
      const red = 255;
      const blue = 0;
      return `linear-gradient(to right, rgb(${red}, 0 , ${blue}), rgb(${red}, ${green}, ${blue}))`;
    },
  },
  methods: {
    updateKarma(event) {
      this.$emit("update-karma", Number(event.target.value));
    },
  },
  watch: {
    karma(newVal) {
      this.$emit("update-karma", newVal);
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
  background: #d3d3d3;
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
  background: #6670c9;
  cursor: pointer;
}

.slider-container input[type="range"]::-moz-range-thumb {
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: #6670c9;
  cursor: pointer;
}
</style>
