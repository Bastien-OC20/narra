<template>
  <div class="dice-roller">
    <button @click="rollDice">Lancer les dés</button>
    <div class="dice-container">
      <div
        v-for="(die, index) in dice"
        :key="index"
        class="die"
        :class="{ rolling: isRolling }"
      >
        {{ die }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dice: [1, 1],
      isRolling: false,
    };
  },
  methods: {
    rollDice() {
      this.isRolling = true;
      setTimeout(() => {
        this.dice = this.dice.map(() => Math.floor(Math.random() * 12) + 1);
        this.isRolling = false;
      }, 1000); // Animation duration
    },
  },
};
</script>

<style scoped>
.dice-roller {
  text-align: left;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  margin-bottom: 20px;
}

.dice-container {
  display: flex;
  justify-content: left;
  gap: 20px;
}

.die {
  width: 50px;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 24px;
  border: 2px solid #000;
  border-radius: 5px;
  background-color: #fff;
  transition: transform 1s;
  color: black;
}

.die.rolling {
  transform: rotate(360deg);
}
</style>
