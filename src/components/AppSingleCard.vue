<script>
export default{
    name: "AppCardList", 
    props: {
        character: Object
    }
}
</script>

<template>
            <img class="" :src="character.img" alt="">
            <h3>{{ character.name }}</h3>
            <p>{{character.category}}</p>
</template>

<style lang="scss" scoped>

img{
    height: 200px;
}

p{
    color: gray;
}
</style>