<template>
    <div>
        <h1> {{ message }} </h1>
    </div>  
</template>

<script>
export default {
    name: 'Header', //non indispensabile ma best practice
    props: ["message"]
}
</script>

<style lang="scss" scoped>

</style>