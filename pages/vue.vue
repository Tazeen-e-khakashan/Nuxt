<template>
<div>
    <h1>{{message}}</h1>
    <div v-if="!showing">Now you can seer</div>
    <div><a v-bind:href="url" >click me</a></div>
    <div v-for-key="sound in sounds">{{sounds}}</div>
    <div v-on:click="toggle">touch</div>
    <div v-bind:style="product">
    <input type="text" v-model="color"/>
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
    }
}
</script>
<style>

</style>