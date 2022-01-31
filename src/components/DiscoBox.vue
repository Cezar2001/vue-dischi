<template>
    <div>
        <img :src="disco.poster" />
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
    div{
        width: 100px;
        height: 100px;
    }
</style>