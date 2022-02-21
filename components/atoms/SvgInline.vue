<template>
    <!-- <div class="icon-svg" v-html="require(`~/assets/icons/search.svg?raw`)" /> -->
    <fa icon="search" />
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
                type: Number,
                default: 'min(24pt, 6vw)'
            },
            spin: {
                type: Boolean,
                default: false
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
    .icon-svg > svg {
        width: var(--size) !important;
        height: var(--size) !important;
    }
    .icon-svg > svg > path {
        fill: red !important;
    }
</style>