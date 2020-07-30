<template>
  <div class="container">
    <div>
   <!--    <Logo /> -->
   <img src="~/assets/lmespic.jpg" style="margin-left:34%">
      <h1 class="title" style="color:blue">
        <nuxt-link to="tasks" >lmestasks..</nuxt-link>  
      </h1>


        <nuxt-link to="tasks" ><h3>9. Route Transitions</h3></nuxt-link> 
        <p>While routing to this page you can notice the transition</p>
       


    </div>
  </div>
</template>

<script>
export default {
 
}
</script>

<style scoped>
.page-enter-active, .page-leave-active{
    transition: all 0.5s;
}
.page-enter, .page-leave-active{
    opacity: 0;
    transform: scale(0);
}
</style>
