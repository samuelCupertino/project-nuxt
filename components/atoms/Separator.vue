<template>
    <hr class="separator" :style="cssVars"/>
</template>

<script> 
    export default {
        name: 'Separator',
        props: {
            margin: {
                type: String,
                default: '5px 0'
            },
            color: {
                type: String,
                default: 'var(--tertiary)'
            },
            height: {
                type: String,
                default: '2px'
            },
            width: {
                type: String,
                default: '100%'
            }
        },
        computed: {
            cssVars() {
                return {
                    '--width': this.width,
                    '--height': this.height,
                    '--margin': this.margin,
                    '--color': this.color
                }
            }
        }
    }
</script>

<style scoped>
    .separator {
        border: none;
        border-radius: 50rem;
        width: var(--width);
        height: var(--height);
        margin: var(--margin);
        background: var(--color);
    }
</style>