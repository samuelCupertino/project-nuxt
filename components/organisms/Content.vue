<template>
    <main class="content">
        <CardUserRepo />
    </main>
</template>
    
<script>
    import CardUserRepo from '../molecules/CardUserRepo.vue'

    export default {
        name: 'Content',
        components: {
            CardUserRepo
        }
    }
</script>

<style scoped>
    .content {
        grid-area: content;
        display: flex;
        background-color: var(--bgSecondary);
        border-radius: min(20px, 5vw);

        padding: var(--gapWidth);
        overflow: hidden;
        transition: background 1s;
    }
</style>