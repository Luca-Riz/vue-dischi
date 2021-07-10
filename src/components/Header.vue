<template>
    <div class="headband mb-5">
        <img src="../assets/logo-spotify.png" alt="logo spotify">

        <select @change="setGenre" v-model="selectedGenre">
            <option value="all" selected="selected">All</option>
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
        position: relative;
        
        img{
            height: 100%;
        };

        select {
            position: absolute;
            right: 2rem;
            top: 50%;
            transform: translate(0, -50%);
        }
    }

</style>