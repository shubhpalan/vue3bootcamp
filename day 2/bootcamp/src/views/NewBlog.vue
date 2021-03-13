<template>
    <div class="container">
        <h1>ADD NEW BLOG</h1>
        <div class="form-input">
            <label for="title">Title</label>
            <input v-model="title" type="text" name="title" id="title">
        </div>
        <div class="form-input">
            <label for="image">Image</label>
            <input @change="getImage" type="file" accept="image/*" name="title" id="image">
        </div>
        <div class="form-input">
            <label for="text">Description</label>
            <textarea v-model="text" name="text" id="text" cols="30" rows="10"></textarea>
        </div>
        
        <div class="form-input" @click="()=>$emit('addBlog',title,image,text)" >
            <input type="button"  class="button" value="Add">
        </div>
        <div class="form-input" @click="()=>$emit('cancel')" >
            <input type="button"  class="button" value="Cancel">
        </div>

    </div>
</template>

<script>
    export default {
        data(){
            return{
                title:"",
                image:null,
                text:""
            }
        },
        methods:{
            getImage(e){
                this.image = e.target.files[0];
            }
        }
    }
</script>

<style>
    input{
        width: 100%;
        padding: 12px 20px;
        margin: 8px 0;
        display: inline-block;
        border: 1px solid #ccc;
        border-radius: 4px;
        box-sizing: border-box;
    }
    .button{
        border: none;
        background: black;
        color: white;

    }
    textarea{
        width: 100%;
        padding: 12px 20px;
        margin: 8px 0;
        display: inline-block;
        border: 1px solid #ccc;
        border-radius: 4px;
        box-sizing: border-box;
    }
    .container{
        width: 100%;
        text-align: center;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .form-input{
    width:500px;
    }

</style>