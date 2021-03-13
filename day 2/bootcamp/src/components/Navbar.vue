<template>
    <div>
        <div class="navbar">
            <span>Blogs</span>
            <ul>
                <router-link v-for="menuitem in menuitems" :to="menuitem.to" :key="menuitem.title">{{ menuitem.title }}</router-link>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
          return{
                menuitems: [
                    {title:"home",to:"/"},
                    {title:"about us",to:"/about"}
                    ],
            }
        }
    }
</script>

<style >
.navbar{
  display:flex;
  width:100%;
  align-items:center;
  position:fixed;
  top:0;
  left:0;
  background:black;
  justify-content:space-between;
  padding:10px;
  
}
ul{
  list-style-type:none;
  display:flex;
  padding-right:50px;
}
a{
  padding: 10px;
  background:black;
  color:white;
  cursor:pointer;
  text-transform: uppercase;
  border: 1px solid white;
  margin: 0 2px;
  border-radius:5px;
  text-decoration: none;
  
}
span{
  color:white;
}
</style>