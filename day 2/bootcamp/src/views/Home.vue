<template>
  <div class="home">
    <!-- <posts v-for="post in posts" :key="post" :title="post.title" :image="post.image" :comments="post.comments" ></posts> -->
  <div  v-if="!addblog" class="">
    <div class="post-container">
      <div class="post" v-for="post in posts" :key="post">
        <blogpost :title="post.title" :image="post.image" :text="post.text" ></blogpost>
      </div>
    </div>
      <input type="button" @click="addblog=true"  class="button" value="Add New Blog">
  </div>
    <div v-else >
      <new-blog @addBlog="addBlog" ></new-blog>

    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Posts from "@/components/Posts.vue";
import blogpost from "@/components/blogpost.vue";
import NewBlog from './NewBlog.vue';

export default {
  name: 'Home',
  components: {
    Posts,
    blogpost,
    NewBlog
  },
  data(){
    return{
      addblog:false,
      posts:[
        {title:"Title 1", image:"https://images.unsplash.com/photo-1569389397653-c04fe624e663?ixid=MXwxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=334&q=80", text:"lorem ipsum"},
        {title:"Title 2", image:"https://images.unsplash.com/photo-1579136223750-d218313097ea?ixlib=rb-1.2.1&ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&auto=format&fit=crop&w=679&q=80", text:"Lorem Ipsum"},
      ],
      message: " World"
    }
  },
  methods:{
    addBlog(title,image,text){
      console.log(title);
      console.log(image);
      console.log(text);
      this.posts.push({title,image:URL.createObjectURL(image),text})
      this.addblog = false;
    }
  }
}
</script>

<style>
  .post-container{
    display: grid;
    grid-template-columns: auto auto auto;
  }
  .post{
    margin:3px
  }
</style>
