<template>
    <div class="headband mb-5">
        <img src="../assets/logo-spotify.png" alt="logo spotify">

        <select name="" id="">
            <option value="all">All</option>
            <option v-for="( genre, index ) in arrayGenres" :key="index" value="genre">{{genre}}</option>

        </select>
        

    
    </div>  
</template>

<script>

export default {
    name: 'Header', //non indispensabile ma best practice
    components: {
        
    },
    props: {
        arrayGenres: {
            type: Array,
            required: true
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