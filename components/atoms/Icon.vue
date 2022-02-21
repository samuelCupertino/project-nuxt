<template>
    <fa class="icon" :style="cssVars" :icon="name" />
</template>

<script>
    export default {
        name: 'Icon',
        props: {
            name: {
                type: String,
                required: true
            },
            size: {
                type: String,
                default: 'min(24pt, 6vw)'
            }
        },
        computed: {
            cssVars() {
                return {
                    '--size': this.size
                }
            }
        }
    }
</script>

<style scoped>
    .icon {
        font-size: var(--size);
    }
</style>