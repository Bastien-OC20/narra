<template>
    <div class="hero-page">
        <SecondNavBar />
        <h1>Crée ton Héros</h1>
        <div class="selection">
            <div class="selection-container col-6">
                <div class="hero-name">
                    <h2>Nom du Héros</h2>
                    <input type="text" v-model="heroName" placeholder="Entrez le nom du héros" class="form-control">
                </div>
                <div class="heroes">
                    <h2>Classes</h2>
                    <div class="card-container">

                        <HeroCard v-for="hero in heroes" :key="hero" :hero="hero"
                            :imageSrc="`/path/to/hero/images/${hero.toLowerCase()}.jpg`"
                            :isSelected="selectedHero === hero" @select-hero="selectHero" />
                    </div>
                </div>
                <div class="species">
                    <h2>Espèces</h2>
                    <div class="card-container">

                        <SpeciesCard v-for="species in speciesList" :key="species" :species="species"
                            :imageSrc="`/path/to/species/images/${species.toLowerCase()}.jpg`"
                            :isSelected="selectedSpecies === species" @select-species="selectSpecies" />
                    </div>
                </div>

                <div class="sliders">
                    <KarmaSlider :karma="karma" @update-karma="updateKarma" />
                    <MoralitySlider :morality="morality" @update-morality="updateMorality" />
                </div>
            </div>
            <div class="selection-container col-6">
                <CharacterPreview :hero="selectedHero" :species="selectedSpecies" />
            </div>
        </div>
        <div class="univers col-12">
            <h2>Univers</h2>
            <div class="card-container">
                <UniversCard v-for="univers in universList" :key="univers" :univers="univers"
                    :imageSrc="`/path/to/univers/images/${univers.toLowerCase()}.jpg`"
                    :isSelected="selectedUnivers === univers" @select-univers="selectUnivers" />
            </div>
        </div>
        <button @click="submitSelection" class="btn btn-primary mt-3">Let's Play</button>
    </div>
</template>

<script>
import HeroCard from '@/components/HeroCard.vue';
import SpeciesCard from '@/components/SpeciesCard.vue';
import UniversCard from '@/components/UniversCard.vue';
import KarmaSlider from '@/components/KarmaSlider.vue';
import MoralitySlider from '@/components/MoralitySlider.vue';
import SecondNavBar from '../components/SecondNavBar.vue';
import CharacterPreview from '@/components/CharacterPreview.vue';

export default {
    components: {
        HeroCard,
        SpeciesCard,
        UniversCard,
        KarmaSlider,
        MoralitySlider,
        SecondNavBar,
        CharacterPreview
    },
    data() {
        return {
            selectedHero: '',
            selectedSpecies: '',
            selectedUnivers: '',
            heroName: '',
            karma: 50,
            morality: 50,
            heroes: ['Guerrier', 'Mage', 'Archer', 'Voleur'],
            speciesList: ['Humain', 'Elfe', 'Nain', 'Orc'],
            universList: ['Fantasy', 'Sci-Fi', 'Steampunk', 'Post-Apocalyptic']
        };
    },
    methods: {
        selectHero(hero) {
            this.selectedHero = hero;
        },
        selectSpecies(species) {
            this.selectedSpecies = species;
        },
        selectUnivers(univers) {
            this.selectedUnivers = univers;
        },
        updateKarma(value) {
            this.karma = value;
        },
        updateMorality(value) {
            this.morality = value;
        },
        submitSelection() {
            console.log('Nom du Héros:', this.heroName);
            console.log('Héros sélectionné:', this.selectedHero);
            console.log('Espèce sélectionnée:', this.selectedSpecies);
            console.log('Univers sélectionné:', this.selectedUnivers);
            console.log('Karma:', this.karma);
            console.log('Moralité:', this.morality);
            // Redirige vers la page play avec les paramètres
            this.$router.push({
                path: '/play',
                query: {
                    heroName: this.heroName,
                    selectedHero: this.selectedHero,
                    selectedSpecies: this.selectedSpecies,
                    selectedUnivers: this.selectedUnivers,
                    karma: this.karma,
                    morality: this.morality
                }
            });
        }
    }
}
</script>

<style >
.hero-page {
  margin: 0 auto;
  padding: 2rem;
  text-align: center;
  position: relative;
}

.hero-name {
    margin-bottom: 2rem;
}


.selection {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
}

.selection-container {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  margin-top: 2rem;
}

.card-container {
  display: flex;
  flex-wrap: wrap;
}

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

.sliders {
    max-width: 400px;;
  margin-top: 2rem;
}

.slider-container {
  margin-bottom: 1rem;
}

input[type="range"] {
  width: 100%;
}

.univers {
  margin-top: 2rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
</style>