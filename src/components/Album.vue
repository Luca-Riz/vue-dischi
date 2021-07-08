<template>
    <div class="headband">
        <img src="../assets/logo-spotify.png" alt="logo spotify">
    </div>  
</template>

<script>
// import 'axios'; <-- altro modo per importarlo
import axios from 'axios';
export default {
    name: 'Album', //non indispensabile ma best practice
    data() {
        return {
            apiURL : 'https://flynn.boolean.careers/exercises/api/array/music',
            albumList : []
        }
    },
    created(){
        this.getAlbums();
    },
    methods: {
        getAlbums(){
            axios
                .get(this.apiURL)
                .then(res => {
                    console.log(res.data);
                })
        }
    }
}
</script>

<style lang="scss" scoped>

    .headband { 
        height: 80px;
        background-color: #2e3a46;
        
        img{
            height: 100%;
        }
    }

</style>