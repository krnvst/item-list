<template>
    <div class="avatar">
        <img class="avatar__img" :src="avatar" alt="user">
    </div>
</template>

<script>
export default {
    name: 'ItemAvatar',
    props: {
        avatar: {
            type: String,
            default: 'https://i.pinimg.com/originals/51/f6/fb/51f6fb256629fc755b8870c801092942.png'
        }
    }
}
</script>

<style scoped>
    .avatar {
        width: 20px;
        height: 20px;
        border-radius: 50%;
    }

    .avatar__img {
        width: 20px;
        height: 20px;
        border-radius: 50%;
    }
</style>