<template>
    <div class="container" @click="toggleVisibility">
        <Icon class="icon-profile" name="circle-user" size="min(16pt, 8vw)" />
    </div>
</template>

<script>
    import Icon from '../atoms/Icon.vue'

    export default {
        name: 'ToggleProfileVisibility',
        components: {
            Icon
        },
        methods: {
            toggleVisibility() {
                const layout = document.querySelector('.layout')
                layout.classList.toggle('profile-visible')
            }
        }
    }
</script>

<style scoped>
    .icon-profile {
        display: none;
    }
    
    @media (max-width: 768px) {
        .icon-profile {
            display: block;
            color: var(--textTertiary);
            cursor: pointer;
            transition-duration: 0.5s;
        }
        .icon-profile:hover,
        .layout.profile-visible .icon-profile {
            color: var(--secondary);
        }
    }
</style>