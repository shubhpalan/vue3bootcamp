<template>
    <div>
        <h1>{{ title }}</h1>
        <img :src="image" width="300" height="300" style="object-fit:cover">
        <p>{{ text }}</p>
    </div>
</template>

<script>
    export default {
        props:["image","title","text"],
        data(){
            return{

            }
        }
    }
</script>

<style>

</style>