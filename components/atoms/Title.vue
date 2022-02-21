<template>
    <h1 class="title" :style="cssVars">
        <slot />
    </h1>
</template>

<script> 
    export default {
        name: 'Title',
        props: {
            fontSize: {
                type: String,
                default: '16pt'
            },
            color: {
                type: String,
                default: 'var(--textPrimary)'
            },
            margin: {
                type: String,
                default: '0'
            },
        },
        computed: {
            cssVars() {
                return {
                    '--fontSize': this.fontSize,
                    '--color': this.color,
                    '--margin': this.margin
                }
            }
        }
    }
</script>

<style scoped>
    .title {
        font-size: var(--fontSize);
        color: var(--color);
        margin: var(--margin);
    }
</style>