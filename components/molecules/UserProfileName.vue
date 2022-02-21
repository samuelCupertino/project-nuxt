<template>
    <div class="profile-name" :style="cssVars">
        <Title class="name" fontSize="min(16pt, 5vw)">Samuel Cupertino</Title>
        <div class="login">
            <Paragraph fontSize="min(12pt, 4vw)" lineHeight="min(14px, 4.5vw)">@samuelCupertino</Paragraph>
            <Icon class="icon-copy" name="clone" size="min(12pt, 4vw)" />
        </div>
    </div>
</template>

<script>
    import Icon from '../atoms/Icon.vue'
    import Title from '../atoms/Title.vue'
    import Paragraph from '../atoms/Paragraph.vue'

    export default {
        name: 'UserProfileName',
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
        },
        components: {
            Icon,
            Title,
            Paragraph
        }
    }
</script>

<style scoped>
    .profile-name {
        color: white;
        display: flex;
        flex-direction: column;
        align-items: center;
        align-items: center;
        gap: min(4px, 1vw);
        margin: var(--margin);
    }

    .profile-name .login {
        font-size: 12pt;
        display: flex;
        align-items: center;
        gap: 5px;
    }

    .icon-copy {
        color: var(--primary);
        cursor: pointer;
        transition-duration: 1s;
    }
    .icon-copy:hover {
        color: var(--secondary);
    }
</style>
