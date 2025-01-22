<template>
    <div class="slider-container">
        <label for="karma">Karma:</label>
        <div class="flex row justify-content-between">
        <p>Chaotique</p><p>Héroïque</p>
        <input type="range" id="karma" v-model="karma" min="0" max="100">
        
        </div>
        <span>{{ karma }}</span>
    </div>
</template>

<script>
export default {
  props: {
    karma: {
      type: Number,
      required: true
    }
  },
  methods: {
    updateKarma(event) {
      this.$emit('update-karma', Number(event.target.value));
    }
  },
  watch: {
    karma(newVal) {
      this.$emit('update-karma', newVal);
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