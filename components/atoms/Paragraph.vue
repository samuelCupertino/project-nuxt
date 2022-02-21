<template>
    <p class="paragraph" :style="cssVars">
        <slot />
    </p>
</template>

<script> 
    export default {
        name: 'Paragraph',
        props: {
            fontSize: {
                type: String,
                default: '12pt'
            },
            lineHeight: {
                type: String,
                default: 'normal'
            },
            maxLine: {
                type: Number,
                default: 999999
            },
            color: {
                type: String,
                default: 'var(--textPrimary)'
            },
        },
        computed: {
            cssVars() {
                return {
                    '--fontSize': this.fontSize,
                    '--color': this.color,
                    '--lineHeight': this.lineHeight,
                    '--maxLine': this.maxLine
                }
            }
        }
    }
</script>

<style scoped>
    .paragraph {
        font-size: var(--fontSize);
        color: var(--color);
        line-height: var(--lineHeight);

        display: -webkit-box;
        overflow: hidden;
        text-overflow: ellipsis;
        -webkit-box-orient: vertical;
        -webkit-line-clamp: var(--maxLine);
    }
</style>