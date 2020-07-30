<template>
  <div class="container">
    <div>
   <!--    <Logo /> -->
   <img src="~/assets/lmespic.jpg" style="margin-left:34%">
      <h1 class="title" style="color:blue">
        <nuxt-link to="tasks" >lmestasks..</nuxt-link>  
      </h1>


      
      

        
        <nuxt-link to="tasks" ><h3>6. Loader Customisation   </h3></nuxt-link> 
        <p>Loader shows us</p>
   
     
     
     
     
     
     
     

     
     





    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "loader",
    };
  },
  
  mounted() {
    setTimeout(() => {
      // Extend loader for an additional 5s
      this.$nuxt.$loading.start();
    }, 2000);
  },
};
</script>

<style>

</style>
