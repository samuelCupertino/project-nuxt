<template>
    <aside class="profile">
        <ImageCircle 
            src="https://github.com/samuelCupertino.png" 
            alt="foto de samuel cupertino" 
            size="85%"
            margin="min(5px, 2vw) 0"
        />
        <UserProfileName/>
        <UserProfileData margin="min(10px, 2vw) 0"/>
        <UserProfileRepos />
    </aside>
</template>
    
<script>
    import ImageCircle from '../atoms/ImageCircle.vue'
    import UserProfileData from '../molecules/UserProfileData.vue'
    import UserProfileName from '../molecules/UserProfileName.vue'
    import UserProfileRepos from '../molecules/UserProfileRepos.vue'
    
    export default {
        name: 'ProfileBar',
        components: {
            ImageCircle,
            UserProfileData,
            UserProfileName,
            UserProfileRepos
        }
    }
</script>

<style scoped>
    .profile {
        grid-area: profile;
        background-color: var(--bgSecondary);
        border-radius: min(20px, 5vw);
        padding: min(20px, 5vw);
        box-sizing: border-box;
        display: flex;
        flex-direction: column;
        align-items: center;
        z-index: 2;
        overflow: hidden auto;
        transition: 1s;
    }

    @media (max-width: 768px) {
        .layout.profile-visible  .profile {
            transform: translateX(calc(-1 * var(--profileWidth) - var(--gapWidth)));
            box-shadow: max(-50px, -10vw) 0 50px 0 var(--bgTertiary);
        }
    }
</style>