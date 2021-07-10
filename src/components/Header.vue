<template>
    <div class="headband mb-5">
        <img src="../assets/logo-spotify.png" alt="logo spotify">

        <select @change="setGenre" v-model="selectedGenre" name="" id="">
            <option selected value="all">All</option>
            <option v-for="( genre, index ) in arrayGenres" :key="index" :value="genre">{{genre}}</option>

        </select>
        

    
    </div>  
</template>

<script>

export default {
    name: 'Header', //non indispensabile ma best practice
    components: {
        
    },

    data() {
        return {
            selectedGenre: ''
        }
    },

    props: {
        arrayGenres: {
            type: Array,
            required: true
        }
    },

    methods: {
        setGenre: function(){
            // console.log(this.selectedGenre);
            this.$emit('getGenre', this.selectedGenre);
        }
    },
};



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