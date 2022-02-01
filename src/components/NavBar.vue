<template>
    <div class="container">
        <div>
            <img src="https://th.bing.com/th/id/R.cdbd7c0bd0c0324064ea876f18d936f9?rik=deMnRk0z%2f9v1Bg&riu=http%3a%2f%2fwww.pearlinux.fr%2fwp-content%2fuploads%2f2017%2f04%2fspotify-music.png&ehk=%2bbtZ94TR91Bvdo2%2fAplSAwxghO6L1IEQe%2fnrBYvQYRE%3d&risl=&pid=ImgRaw&r=0&sres=1&sresct=1" />
        </div>
        <div>
            <select @change="$emit('genre',$event)">
                <option value="">All genre</option>
                <option value="rock">Rock</option>
                <option value="pop">Pop</option>
                <option value="jazz">Jazz</option>
                <option value="metal">Metal</option>
            </select>
        </div>
        <div>
            <select @change="$emit('authors',$event)">
                <option value="">All Authors</option>
                <option value="bon jovi">Bon Jovi</option>
                <option value="queen">Queen</option>
                <option value="sting">Sting</option>
                <option value="steve gadd band">Steve Gadd Band</option>
                <option value="iron maiden">Iron Maiden</option>
                <option value="eric clapton">Eric Clapton</option>
                <option value="deep purple">Deep Purple</option>
                <option value="metallica">Mettalica</option>
                <option value="dave weckl">Dave Weckl</option>
                <option value="michael jacjson">Micheal Jackson</option>
            </select>
        </div>
        
    </div>    
</template>

<script>
export default {
    
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';
.container{
    background-color: $grey-background;
    height: 70px;
    margin-bottom: 80px;
    display: flex;
    align-items: center;
    padding: 10px;
    
    img{
        height: 50px;
    }

    select{
        margin-left: 25px;
        padding: 5px;
        width: 100px;
        border-radius: 15px;
        appearance: none;
        cursor: pointer;    
    }
}
</style>