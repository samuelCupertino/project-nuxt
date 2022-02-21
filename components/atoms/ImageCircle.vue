<template>
    <img 
        class="image-circle" 
        :style="cssVars"
        :src="src"
        :alt="alt"
    />
</template>

<script> 
    export default {
        name: 'ImageCircle',
        props: {
            src: {
                type: String,
                required: true
            },
            alt: {
                type: String,
                required: true
            },
            size: {
                type: String,
                default: '100%'
            },
            margin: {
                type: String,
                default: '0'
            },
            bgColor: {
                type: String,
                default: 'transparent'
            }
        },
        computed: {
            cssVars() {
                return {
                    '--size': this.size,
                    '--margin': this.margin,
                    '--bgColor': this.bgColor
                }
            }
        }
    }
</script>

<style scoped>
    .image-circle {
        width: var(--size);
        aspect-ratio: 1;
        margin: var(--margin);
        background-color: var(--bgColor);
        border-radius: 50%;
        object-fit: cover;
    }
</style>