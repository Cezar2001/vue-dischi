<template>
    <div class="img-container">
        <div>
            <img :src="disco.poster" />
            <h3>{{ disco.title }}</h3>
            <div class="info">{{ disco.author }}</div>
            <div class="info">{{ disco.year }}</div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        disco: Object
    }
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';
.img-container{
    width: 200px;
    height: 350px;
    text-align: center;
    background: $grey-background;
    margin: 10px 15px;
    img{
        width: 100%;
        padding: 15px;
    }
    h3{
        color: $white-color;
        padding: 15px 0;
    }
    .info{
        color: $grey-color;
    }
}
</style>