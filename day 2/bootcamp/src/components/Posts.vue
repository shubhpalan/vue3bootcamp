<template>
    <div>
        <div class="container">
        <div class="heading">{{ title }}</div>
        <div class="image"> <img :src="image" width="300" alt=""></div>
        <div class="comments">
        Comments:
            <div v-for="comment in comments" class="comment" :key="comment" >{{ comment }}</div>
                <div class="addcomment"><input type="text" v-model="newComment"> <button @click="addComment">+</button></div>
            </div>
         </div>
    </div>
</template>

<script>
    export default {
        name:"Posts",
        props: ["title","image","comments"] ,
        data(){
        return{
            newComment:"",
        }
     },
  methods:{
    addComment(){
         this.comments.push(this.newComment);
          this.newComment = ""
       }
     }
        
    }
</script>

<style lang="scss" scoped>

</style>