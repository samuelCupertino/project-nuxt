<template>
    <ScrollVertical>
        <ul class="profile-repos">
            <li v-for="repo in 20" :key="repo">
                <article class="repo">
                    <Title fontSize="min(12pt, 5vw)" margin="0 0 min(10px, 3vw)" color="var(--textSecondary)">project-base-vue</Title>
                    <Paragraph fontSize="min(10pt, 4vw)" lineHeight="min(14pt, 5.5vw)" :maxLine="3" color="var(--textTertiary)">But I must explain to you how all idea of pleasure and praising pain was born and I will give you.</Paragraph>
                </article>
            </li>
        </ul>
    </ScrollVertical>
</template>

<script>
    import Icon from '../atoms/Icon.vue'
    import ScrollVertical from '../atoms/ScrollVertical.vue'
    import Title from '../atoms/Title.vue'
    import Paragraph from '../atoms/Paragraph.vue'    

    export default {
        name: 'UserProfileRepos',
        components: {
            Icon,
            ScrollVertical,
            Title,
            Paragraph
        }
    }
</script>

<style scoped>
    .profile-repos {
        display: flex;
        flex-direction: column;
    }

    .repo {
        background-color: var(--bgTertiary);
        padding: min(10px, 3.5vw);
        border-radius: 10px;
        margin: min(5px, 1.5vw) 0px;
        border: 1px solid var(--bgTertiary);
        transition-duration: 0.5s;
    }    
    .repo:hover {
        border-color: var(--secondary);
    }
</style>
