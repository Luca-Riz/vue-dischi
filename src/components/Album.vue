<template>
    <div class="row row-cols-2 row-cols-md-4 row-cols-lg-5">
        <div v-for="(album,index) in albumList" 
            :key="index" class="col px-4 my-2">
            <div class="headband">
                <img class="py-4" :src="album.poster" alt="#">
                <h3 class="title pb-4 text-uppercase text-center"> {{ album.title }} </h3>
                <div class="author text-center"> {{ album.author }} </div>
                <div class="year text-center"> {{ album.year }} </div>
            </div>
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
    
    .headband{
        display: flex;
        flex-direction: column;
        align-items: center;
        background-color: #2e3a46;
        color: white;
        height: 100%;

        &:last-child {
            margin-bottom: 3rem;
        }

        img {
            width: 80%;
        }

        .author, .year {
            color: grey
        }
    }

</style>