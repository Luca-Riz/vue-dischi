<template>
    <div class="row row-cols-2 row-cols-md-4 row-cols-lg-5">
        <div v-for="(album,index) in albumList" 
            :key="index" class="headband col px-4 my-2">
            <img :src="album.poster" alt="#">
            {{ album.title }}
        </div>          
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
                    // console.log(res.data.response);
                    this.albumList = res.data.response;
                    console.log(this.albumList.response);
                    })
        }
    }
}
</script>

<style lang="scss" scoped>

</style>