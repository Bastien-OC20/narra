<template>
  <div class="play-page">
    <SecondNavBar />
    <div class="top-section">
      <CharacterStats :heroName="heroName" :selectedHero="selectedHero" :selectedSpecies="selectedSpecies"
        :selectedUnivers="selectedUnivers" :karma="karma" :morality="morality" />
      <NarrationPrompt :narration="narration" />
    </div>
    <div class="bottom-section">
      <HeroChoices :choices="choices" @select-choice="handleChoice" />
      <Historique :historique="historique" />
    </div>
  </div>
</template>

<script>
import CharacterStats from '@/components/CharacterStats.vue';
import NarrationPrompt from '@/components/NarrationPrompt.vue';
import HeroChoices from '@/components/HeroChoices.vue';
import SecondNavBar from '../components/SecondNavBar.vue';
import Historique from '@/components/Historique.vue';

export default {
  name: 'PlayPage',
  components: {
    CharacterStats,
    NarrationPrompt,
    HeroChoices,
    SecondNavBar,
    Historique
  },
  data() {
    return {
      heroName: this.$route.query.heroName || '',
      selectedHero: this.$route.query.selectedHero || '',
      selectedSpecies: this.$route.query.selectedSpecies || '',
      selectedUnivers: this.$route.query.selectedUnivers || '',
      karma: this.$route.query.karma || 50,
      morality: this.$route.query.morality || 50,
      narration: 'Vous vous trouvez dans une forêt sombre et mystérieuse...',
      choices: ['Explorer la forêt', 'Retourner au village', 'Monter un camp']
    };
  },
  methods: {
    handleChoice(choice) {
      console.log('Choix du Héros:', choice);
      this.historique.push(`Choix: ${choice}`);
    }
  }
}
</script>

<style scoped>
.play-page {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100vh;
  padding: 2rem;
}

.top-section {
  display: flex;
  justify-content: space-between;
}

.bottom-section {
  margin-top: auto;
}

.character-stats {
  flex: 1;
  margin-right: 2rem;
}

.narration-prompt {
  flex: 2;
}

.bottom-section {
  display: flex;
  justify-content: space-between;
}
</style>