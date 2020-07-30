<template>
  <div class="container">
    <div>
   <!--    <Logo /> -->
   <img src="~/assets/lmespic.jpg" style="margin-left:34%">
      <h1 class="title" style="color:blue">
        <nuxt-link to="tasks" >lmestasks..</nuxt-link>  
      </h1>


      
      
 
        <nuxt-link to="tasks" ><h3>2. Mounted   </h3></nuxt-link>  
     
          <p>{{ title }}</p>
        
     
     
     
     
     
     
     
     
     

     
     





    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "temp data",
    };
  },
  mounted () {
    const self = this
    setTimeout(() => {
      // Extend loader for an additional 5s
      self.$nuxt.$loading.start()
      self.title = 'hello im changed here  after mounted and overwrited the  temp data'
    }, 1000)
  }
};
</script>

<style>

</style>
