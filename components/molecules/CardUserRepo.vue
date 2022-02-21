<template>
    <ScrollVertical>
        <ul class="container">
            <li v-for="(repo, i) in 20" :key="repo">
                <article class="user-repo">
                    <ul class="repo-icons">
                        <li class="repo-icon">
                            <Icon name="heart" size="min(16pt, 6vw)" class="icon-like"/>
                        </li>
                        <li class="repo-icon">
                            <Icon name="star" size="min(14pt, 6vw)" />
                            <span>15</span>
                        </li>
                        <li class="repo-icon">
                            <Icon name="code-fork" size="min(14pt, 5vw)"/>
                            <span>15</span>
                        </li>
                    </ul>
                    <div class="repo-content">
                        <ImageCircle 
                            class="user-avatar"
                            :src="`https://randomuser.me/api/portraits/${Math.random() > 0.5 ? 'men':'women'}/${i}.jpg`" 
                            alt="foto do proprietario do repositorio" 
                            size="min(60px, 15vw)"
                        />
                        <Title fontSize="min(12pt, 3.5vw)" margin="0 0 min(10px, 4vw)" color="var(--textSecondary)">But I must explain</Title>
                        <Paragraph fontSize="min(10pt, 3.5vw)" lineHeight="min(14pt, 5vw)" :maxLine="3" color="var(--textTertiary)">But I must explain to you how all this mistaken idea of denouncing pleasure and praising pain was born and I will give you a complete account of the system, and expound the actual teachings of the great explorer of the truth, the master-builder of human happiness.</Paragraph>
                    </div>
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
    import ImageCircle from '../atoms/ImageCircle.vue'

    export default {
        name: 'CardUserRepo',
        components: {
            Icon,
            ScrollVertical,
            Title,
            Paragraph,
            ImageCircle
        }
    }
</script>

<style scoped>
    .container {
        display: grid;
        gap: min(20px, 5vw);
        grid-template-columns: repeat(auto-fill, minmax(min(100%, 240px), 1fr));
    }

    .user-repo {
        display: flex;
        flex-direction: column;
        gap: min(10px, 10vw);
        padding: min(10px, 3vw);
        border-radius: min(15px, 5vw);
        border: 1px solid transparent;
        background-color: var(--bgTertiary);
        background-image: linear-gradient(135deg, var(--bgSecondary), var(--primary), var(--secondary), var(--bgSecondary));
        background-size: 100% 0%;
        background-repeat: no-repeat;
        background-position: bottom;
        transition-duration: 0.5s;
    }
    .user-repo:hover {
        background-size: 100% 100%;
        border-color: var(--secondary);
    }

    .repo-icons {
        display: flex;
        align-items: center;
        gap: min(10px, 5vw);
        padding-right: 75px;
        color: var(--tertiary);
        transition: 1s;
    }
    .user-repo:hover .repo-icons {
        color: var(--bgSecondary);
    }
    .repo-icon {
        display: flex;
        align-items: center;
        gap: min(3px, 1vw);;
        font-size: min(12pt, 5vw);
        font-weight: bolder;
        cursor: default;
    }
    .repo-icon .icon-like {
        color: var(--textSecondary);
        cursor: pointer;
        transition: 0.5s;
    }
    .repo-icon .icon-like:hover {
        color: var(--secondary);
        transform: scale(1.25);
    }

    .repo-content {
        background-image: linear-gradient(200deg, var(--bgPrimary) 30%, rgb(0 0 0 / 40%));
        padding: min(10px, 3vw);
        border-radius: min(10px, 3vw);;
    }
    .user-avatar {
        margin-left: auto;
        display: block;
        margin-top: max(-60px, -15vw);
        transform: translateY(50%);
        border: min(5px, 1vw) solid var(--bgPrimary);
        box-sizing: border-box;
    }
</style>
