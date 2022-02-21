<template>
    <div class="scroll-vertical" :style="cssVars">
        <slot />
    </div>
</template>

<script> 
    export default {
        name: 'ScrollVertical',
        props: {
            margin: {
                type: String,
                default: '0'
            }
        },
        computed: {
            cssVars() {
                return {
                    '--margin': this.margin
                }
            }
        }
    }
</script>

<style scoped>
    .scroll-vertical {
        display: flex;
        flex: 1;
        width: 100%;
        flex-direction: column;
        position: relative;
        overflow: hidden scroll;
        border-radius: 20px;
        margin: var(--margin);
    }
    .scroll-vertical::before, 
    .scroll-vertical::after {
        content: "";
        width: 100%;
        padding: 15px 0px;
        position: sticky;
        margin-top: -30px;
        pointer-events: none;
        z-index: 1;
    }
    .scroll-vertical::before {
        top: 0px;
        background-image: linear-gradient(var(--bgSecondary), transparent);
    }
    .scroll-vertical::after {
        bottom: 0px;
        background-image: linear-gradient(transparent, var(--bgSecondary));
    }

    .scroll-vertical > *:first-child {
        margin-top: 5px;
    }
    .scroll-vertical > *:last-child {
        margin-bottom: 5px;
    }

    .scroll-vertical > * {
        transition: 0;
    }
    .scroll-vertical:hover > * {
        padding-right: 5px;
    }
    .scroll-vertical:hover {
        width: calc(100% + 10px);
        margin-right: -10px;
    }
</style>