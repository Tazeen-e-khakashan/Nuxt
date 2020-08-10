<template>
  <div class="container">
    <div>
   <!--    <Logo /> -->
   <img src="~/assets/lmespic.jpg" style="margin-left:34%">
      <h1 class="title" style="color:blue">
        <nuxt-link to="tasks" >lmestasks..</nuxt-link>
      </h1>





        <nuxt-link to="" ><h3>*Skill Share Course Basics* </h3></nuxt-link>
        <nuxt-link to="posts" ><h3>*1.Posts* </h3></nuxt-link>
        <nuxt-link to="comments" ><h3>*2.Commemts* </h3></nuxt-link>
        <nuxt-link to="comments" ><h3>*3.Albums* </h3></nuxt-link>
        <nuxt-link to="comments" ><h3>*4.Photos* </h3></nuxt-link>
        <nuxt-link to="comments" ><h3>*5.Todos* </h3></nuxt-link>
        <nuxt-link to="comments" ><h3>*6.Users* </h3></nuxt-link>
        <nuxt-link to="task1" ><h3>1. asyncData</h3></nuxt-link>
        <nuxt-link to="task2" ><h3>2. Mounted   </h3></nuxt-link>
        <nuxt-link to="task3" ><h3>3. Middleware </h3></nuxt-link>
        <nuxt-link to="task4" ><h3>4. Dynamic routing ( params ) </h3></nuxt-link>
        <nuxt-link to="task5" ><h3>5. Query Params    </h3></nuxt-link>
        <nuxt-link to="task6" ><h3>6. Loader Customisation   </h3></nuxt-link>
        <nuxt-link to="task7" ><h3>7. Layouts   </h3></nuxt-link>
        <nuxt-link to="task8" ><h3>8. CSS</h3></nuxt-link>
        <nuxt-link to="task9" ><h3>9. Route Transitions</h3></nuxt-link>
        <nuxt-link to="task10" ><h3>10. I18n </h3></nuxt-link>



















    </div>
  </div>
</template>

<script>
export default {}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;

  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.slave{
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}
.links {
  padding-top: 15px;
}
.ab{background-color: yellow;
color:blue;


}
</style>
