<template>
    <div>
        <disco-box v-for="(disco, index) in discoList" 
        :key="index" 
        :disco="disco"/>
    </div>
</template>

<script>
import DiscoBox from './DiscoBox.vue'; 
export default {
    components: {
        DiscoBox
    },
    props: {
        discoList: Array
    }
}
</script>

<style lang="scss" scoped>
div{
    // display: flex;
    // flex-wrap: wrap;
    // justify-content: space-around;
    // text-align: center;
    // padding: 25px;
    height: 150px;
}
</style>