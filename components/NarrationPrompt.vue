<template>
    <div class="narration-prompt">
        <h2>Narration</h2>
        <p>{{ narration }}</p>
    </div>
</template>

<script>
export default {
    props: {
        narration: String
    }
}
</script>

<style scoped>
.narration-prompt {
    text-align: left;
    margin-bottom: 2rem;
}
</style>