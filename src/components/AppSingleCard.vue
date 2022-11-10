<script>
export default{
    name: "AppCardList", 
    props: {
        character: Object
    }
}
</script>

<template>
            <img class="" :src="character.image" alt="">
            <h3>{{ character.name }}</h3>
</template>

<style lang="scss" scoped>

</style>