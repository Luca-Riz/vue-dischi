<template>
    <div class="container">

        <Album :arrayAlbum="arrayAlbum" />
        
    </div>
</template>

<script>
import Album from '@/components/Album.vue';
export default {
    name: 'Main', //non indispensabile ma best practice
    components: {
    Album
    },
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
    
</style>