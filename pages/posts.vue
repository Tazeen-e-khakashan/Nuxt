<template>
<div class=" mx-6 my-4 px-2">
    <h1>{{message}}</h1>
    <div v-if="!showing">Now you can seer</div>
    <div><a v-bind:href="url" >click me</a></div>
    <div v-for="sound in sounds" :key="sound">{{sound}}</div>
    <div v-on:click="toggle">touch</div>
    <div v-bind:style="product">
    <input type="text" v-model="color"/>
    </div>
    <div>
        <table class="table-auto">
            <thead>
                <tr>
                    <th  class="px-4 py-2">User Id</th>
                    <th  class="px-4 py-2">Title</th>
                    <th  class="px-4 py-2">Body</th>
                </tr>
            </thead>
            <tbody>
                <tr  v-for="post in posts" :key="post.id">
                    <td class="border px-4 py-2">{{ post.id }}</td>
                    <td class="border px-4 py-2">{{ post.title }}</td>
                    <td class="border px-4 py-2">{{ post.body }}</td>
                </tr>
            </tbody>

        </table>

     </div>

</div>
</template>
<script>
export default {
    data(){
        return{
            message:"Hello World!",
            showing:false,
            url:"https://www.google.com",
            sounds:['boom','clap','taz','rez'],
            color:"purple"};

    },
    computed:{
        product:function(){

                var styleObject ={
                    backgroundColor:this.color,

                }
              return styleObject;
        }
    },
    methods:{
        toggle:function(){
            console.log('clicked');
        }
    },
    asyncData ({$axios}){
        return $axios.get('https://jsonplaceholder.typicode.com/posts')
        .then(response =>{
             return{posts:response.data}
        });

    },
}
</script>
<style>

</style>