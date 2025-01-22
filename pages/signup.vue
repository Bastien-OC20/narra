<template>
    
    <div class="signup-page">
        
        <h1>Inscription</h1>
        <form @submit.prevent="signup">
            <div>
                <label for="name">Nom:</label>
                <input type="text" id="name" v-model="name" required>
            </div>
            <div>
                <label for="email">Email:</label>
                <input type="email" id="email" v-model="email" required>
            </div>
            <div>
                <label for="password">Mot de passe:</label>
                <input type="password" id="password" v-model="password" required>
            </div>
            <button type="submit">S'inscrire</button>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            name: '',
            email: '',
            password: ''
        };
    },
    methods: {
        signup() {
            // Logique d'inscription
            console.log('Nom:', this.name);
            console.log('Email:', this.email);
            console.log('Mot de passe:', this.password);
        }
    }
}
</script>

<style >
.signup-page {
    max-width: 400px;
    margin: 0 auto;
    padding: 1rem;
    text-align: center;
}

form div {
    margin-bottom: 1rem;
}

label {
    display: block;
    margin-bottom: 0.5rem;
}

input {
    width: 100%;
    padding: 0.5rem;
    box-sizing: border-box;
}

button {
    padding: 0.5rem 1rem;
    background-color: #007BFF;
    color: white;
    border: none;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}
</style>