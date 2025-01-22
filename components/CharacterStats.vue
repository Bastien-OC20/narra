<template>
    <div class="character-stats col-6">
        <h2>Statistiques du Personnage</h2>
        <p>Nom du Héros {{ heroName }}, Classe {{ selectedHero }}, Espèce {{ selectedSpecies }}</p>
        <p>Karma : {{ karma }} et Moralité : {{ morality }}</p>
        <div class="stat">
            <label>Endurance :</label>
            <div class="progress-bar col-4">
                <div class="progress" :style="{ width: stamina + '%' }"></div>
            </div>
        </div>
        <div class="stat">
            <label>Défense :</label>
            <div class="progress-bar col-4">
                <div class="progress" :style="{ width: def + '%' }"></div>
            </div>
        </div>
        <div class="stat" v-if="selectedHero === 'Mage'">
            <label>Mana :</label>
            <div class="progress-bar col-4">
                <div class="progress" :style="{ width: mana + '%' }"></div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  props: {
    heroName: String,
    selectedHero: String,
    selectedSpecies: String,
    selectedUnivers: String,
    karma: Number,
    morality: Number,
    stamina: Number,
    def: Number,
    mana: Number
  }
}
</script>

<style scoped>
.character-stats {
  text-align: left;
  margin-bottom: 2rem;
}
</style>