<template>
  <div class="container">
    <div>
   <!--    <Logo /> -->
   <img src="~/assets/lmespic.jpg" style="margin-left:34%">
      <h1 class="title" style="color:blue">
        <nuxt-link to="tasks" >lmestasks..</nuxt-link>  
      </h1>


      
      
 
        <nuxt-link to="tasks" ><h3>3. Middleware </h3></nuxt-link>  
        <p>Just check the console it will show the middleware before rendering </p>

        
     
     
     
     
     
     
     
     
     

     
     





    </div>
  </div>
</template>

<script>
export default {
  middleware:"test",
}
// export default {
//     middleware({ store, redirect }) {
//       // If the user is not authenticated
//       if (store.state.authenticated) {
//         return redirect(' ')
//       }
//     }
//   }
</script>

<style>

</style>
