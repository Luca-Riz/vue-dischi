<template>
    <section>
        <div class="row row-cols-2 row-cols-md-4 row-cols-lg-5" > 
            <div v-for="(album,index) in arrayAlbum" 
                :key="index" class="col px-4 my-2">
                <div class="headband">
                    <img class="py-4" :src="album.poster" alt="#">
                    <h3 class="title pb-4 text-uppercase text-center"> {{ album.title }} </h3>
                    <div class="author"> {{ album.author }} </div>
                    <div class="year pb-3"> {{ album.year }} </div>

                </div>
            </div>          
        </div>
        
    </section>
</template>

<script>


export default {
    name: 'Album', //non indispensabile ma best practice
    data() {
        return {
    
        }
    },
    props: {
        arrayAlbum: {
            type: Array,
            required: true
        }
    },

    methods: {

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


        img {
            width: 80%;
        }

        .author, .year {
            color: grey
        }
    }

</style>