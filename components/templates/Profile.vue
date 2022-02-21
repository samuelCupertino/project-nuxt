<template>
    <div class="layout">
        <FavoriteBar />
        <Header />
        <ProfileBar />
        <Content />
    </div>
</template>
    
<script>
    import FavoriteBar from '../organisms/NavBar.vue'
    import Header from '../organisms/HeaderBar.vue'
    import ProfileBar from '../organisms/ProfileBar.vue'
    import Content from '../organisms/Content.vue'

    export default {
        name: 'Profile',
        components: {
            FavoriteBar,
            Header, 
            ProfileBar,
            Content
        }
    }
</script>

<style scoped>
    .layout {
        --gapWidth: min(20px, 3vw);
        --favoriteWidth: min(80px, 18vw);
        --contentWidth: calc(100% - var(--favoriteWidth) - var(--gapWidth));
        --profileWidth: min(250px, 60vw);
        --headerHeight: min(60px, 18vw);

        display: grid;
        grid-template-columns: var(--favoriteWidth) auto var(--profileWidth);
        grid-template-rows: var(--headerHeight) calc(100vh - var(--headerHeight) - var(--gapWidth) * 3);
        grid-template-areas:
            "favorite header profile"
            "favorite content profile";
        gap: var(--gapWidth);
        padding: var(--gapWidth);

        width: 100vw;
        height: 100vh;
        overflow: hidden;
        box-sizing: border-box;
        background-color: var(--bgPrimary);
        transition: background 1s;
    }

    @media (max-width: 768px) {
        .layout {
            grid-template-columns: var(--favoriteWidth) var(--contentWidth) var(--profileWidth);
            grid-template-areas:
                "favorite header ."
                "favorite content profile";
        }
    }
</style>