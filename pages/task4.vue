<template>
  <div class="container">
    <div>
   <!--    <Logo /> -->
   <img src="~/assets/lmespic.jpg" style="margin-left:34%">
      <h1 class="title" style="color:blue">
        <nuxt-link to="tasks" >lmestasks..</nuxt-link>  
      </h1>


      
      

     <nuxt-link to="tasks" ><h3>4. Dynamic routing</h3></nuxt-link>   
     <!-- <h2><b>async data using 1 way binding</b></h2>
      <iframe
      width="560"
      height="315"
      :src="videoLink"
      frameborder="0"
      allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
      allowfullscreen
    />  -->
    <h2><b>async data using normal binding</b></h2>
    <li v-for="post in posts" :key="post.id">
      <nuxt-link :to="`/${post.id}`"> {{ post.title }}</nuxt-link>
      </li>
     

     

     
     





    </div>
  </div>
</template>

<script>
export default {
  //  asyncData() {
  //    console.log("server")
  
  //   return {
  //     videoLink: "https://www.youtube.com/embed/uSGYg4qbgqM",
  //   };
  //  },

   asyncData({$axios}){
      return $axios.get('https://jsonplaceholder.typicode.com/posts')
      .then(response => {
          console.log(response)
         return {posts:response.data}
      });
    //    console.log('async data')
    },
// validate(){
//     return true
// }
// data(){
//     return{
//     };
// },


}
</script>

<style>

</style>
