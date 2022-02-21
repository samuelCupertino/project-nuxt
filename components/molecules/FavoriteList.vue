<template>
    <div class="favorite-wrapper">
        <div class="favorite-like">
            <Icon class="icon-likes" name="heart" size="min(34pt, 12vw)"/>
        </div>
        <ScrollVertical :margin="margin">
            <ul class="favorite-list">
                <li class="favorite-user" v-for="(repo, i) in 20" :key="repo" :data-num="parseInt(Math.random() * 5 + 1)">
                    <ImageCircle 
                        :src="`https://randomuser.me/api/portraits/${Math.random() > 0.5 ? 'men':'women'}/${i}.jpg`"  
                        alt="avatar do usuário" 
                    />
                </li>
            </ul>
        </ScrollVertical> 
    </div>
</template>

<script>
    import Icon from '../atoms/Icon.vue'
    import ScrollVertical from '../atoms/ScrollVertical.vue'
    import ImageCircle from '../atoms/ImageCircle.vue'  

    export default {
        name: 'FavoriteList',
        props: {
            margin: {
                type: String,
                default: '0'
            }
        },
        components: {
            Icon,
            ScrollVertical,
            ImageCircle,
        }
    }
</script>

<style scoped>
    .favorite-wrapper { 
        display: contents;
    }
    .favorite-like {
        display: flex;
        justify-content: center;
    }
    .icon-likes {
        color: var(--primary);
        cursor: pointer;
        transition: 1s;
    }
    .icon-likes:hover {
        color: var(--secondary);
    }

    .favorite-list {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 10px;
    }
    .favorite-user {
        width: 85%;
        cursor: pointer;
        border-radius: 50%;
        display: flex;
        border: 2px solid var(--primary);
        position: relative;
        transition: 1s;
    }
    .favorite-user:hover {
        border-color: var(--secondary);
    }
    .favorite-user::after {
        content: attr(data-num);
        color: var(--textTertiary);
        background-color: var(--primary);
        font-size: min(11pt, 4vw);
        font-weight: bolder;
        padding: 0px 3.5px;
        border-radius: 50rem;

        position: absolute;
        bottom: 0;
        right: 0;
        transition: 0.5s;
    }
    .favorite-user:hover::after {
        color: var(--bgTertiary);
        background-color: var(--secondary);
    }
</style>
