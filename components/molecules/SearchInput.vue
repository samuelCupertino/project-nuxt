<template>
    <div class="container">
        <input class="search-input" type="text" placeholder="Search" />
        <Icon class="search-icon" name="search" size="min(16pt, 8vw)" />
    </div>
</template>

<script>
    import Icon from '../atoms/Icon.vue'

    export default {
        name: 'SearchInput',
        components: {
            Icon
        }
    }
</script>

<style scoped>
    .container {
        max-width: 300px;
        display: flex;
        align-items: flex-end;
        border-bottom: 1px solid transparent;
        transition: 1s;
    }
    .container:hover {
        flex: 1;
        border-color: var(--textSecondary);
    }

    .search-icon {
        color: var(--textTertiary);
        cursor: pointer;
        transition-duration: 0.5s;
    }
    .search-icon:hover {
        color: var(--secondary);
    }

    .search-input {
        width: 0;
        padding: 3px 0;
        font-size: min(12pt, 5vw);
        color: var(--textSecondary);
        background-color: transparent;
        border: none;
        opacity: 0;
        transition: 1s;
    }
    .container:hover .search-input {
        width: 100%;
        padding: 3px 5px;
        opacity: 1;
    }
</style>