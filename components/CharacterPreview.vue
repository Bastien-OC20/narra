<template>
    <div class="character">
        <h2>Aperçu du personnage</h2>
        <div class="character-preview">
            <div v-if="hero">
                <img :src="heroImageSrc" @error="setDefaultHeroImage" alt="Hero Image" class="character-image">
            </div>
            <p v-else>Sélectionnez un héros et une espèce pour voir l'aperçu.</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        hero: {
            type: String,
            required: false
        },
        species: {
            type: String,
            required: false
        }
    },
    computed: {
        heroImageSrc() {
            return this.hero ? `/path/to/hero/images/${this.hero.toLowerCase()}.jpg` : '../assets/img/rodeur.png';
        },
    },
    methods: {
        setDefaultHeroImage(event) {
            event.target.src = '../assets/img/rodeur.png';
        },
    }
}
</script>

<style >
.character-preview {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    margin-top: 2rem;
    height: 70vh;
    border: 2px solid black;
    background-color: #f0f0f07c;
}

.character-image {
    width: 50%;
    height: auto;
    margin: 0.5rem;
    
}
</style>