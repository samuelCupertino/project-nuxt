<template>
    <header class="header">
        <SearchInput />
        <ToggleProfileVisibility />
    </header>
</template>
    
<script>
    import SearchInput from '../molecules/SearchInput.vue'
    import ToggleProfileVisibility from '../molecules/ToggleProfileVisibility.vue'
    
    export default {
        name: 'HeaderBar',
        components: {
            SearchInput,
            ToggleProfileVisibility
        }
    }
</script>

<style scoped>
    .header {
        grid-area: header;
        background-color: var(--bgSecondary);
        border-radius: min(20px, 5vw);

        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: min(20px, 5vw);
        padding: min(10px, 5vw) min(20px, 5vw);
        transition: background 1s;
    }
</style>
