<template>
    <div class="container">
        <div>
            <disco-box v-for="(disco,index) in discoList" 
            :key="index" 
            :disco="disco"/>
        </div>
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
.container{
    width: 1200px;
    margin: 0 auto;
    div{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    }
}
</style>