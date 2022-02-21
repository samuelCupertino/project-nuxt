<template>
    <aside class="favorite">
        <ImageCircle 
            src="https://project-base-react.vercel.app/_next/image?url=%2Fgithub-dark.png&w=256&q=75" 
            alt="Github logo" 
        />
        <BtnToggleTheme margin="min(15px, 5vw) 0"/>
        <FavoriteList margin="min(15px, 5vw) 0" />
        <BtnLogout />
    </aside>
</template>
    
<script>
    import ImageCircle from '../atoms/ImageCircle.vue'
    import Icon from '../atoms/Icon.vue'
    import FavoriteList from '../molecules/FavoriteList.vue'
    import BtnLogout from '../molecules/BtnLogout.vue'
    import BtnToggleTheme from '../molecules/BtnToggleTheme.vue'

    export default {
        name: 'NavBar',
        components: {
            ImageCircle,
            FavoriteList,
            BtnLogout,
            Icon,
            BtnToggleTheme
        }
    }
</script>

<style scoped>
    .favorite {
        grid-area: favorite;
        background-color: var(--bgSecondary);
        border-radius: min(30px, 7vw);

        display: flex;
        flex-direction: column;
        padding: min(15px, 5vw) min(10px, 3vw);
        box-sizing: border-box;
        overflow: hidden auto;
        transition: background 1s;
    }

</style>