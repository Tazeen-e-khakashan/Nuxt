<template>
    <div>
        <table class="table-auto">
            <thead>
                <tr>
                    <th  class="px-4 py-2">User Id</th>
                    <th  class="px-4 py-2">Name</th>
                    <th  class="px-4 py-2">Email</th>
                    <th  class="px-4 py-2">Body</th>
                     <th  class="px-4 py-2">Edit</th>
                </tr>
            </thead>
            <tbody>
                <tr  v-for="comment in comments" :key="comment.id">
                    <td class="border px-4 py-2">{{ comment.id }}</td>
                    <td class="border px-4 py-2">{{ comment.name }}</td>
                    <td class="border px-4 py-2">{{ comment.email }}</td>
                    <td class="border px-4 py-2">{{ comment.body }}</td>
                     <td class="border px-4 py-2"> <input type="text" v-model="newUser" @keyup.enter="addUser"></td>
                </tr>
            </tbody>

        </table>
    </div>
</template>
<script>
export default {
    data(){
        return{
                  newUser: '',

        };
    },
    asyncData ({$axios}){
        return $axios.get('https://jsonplaceholder.typicode.com/comments')
        .then(response =>{
             return{comments:response.data}
        });

    },
     addUser() {https://jsonplaceholder.typicode.com/comments
      axios.post('', {
        name: this.newUser
      })
        .then((response) => {
            // console.log(response);
         return{comments:response.data=this.newUser}
        //   const data = response.data;
        //   this.comment.push(data);
        //   this.newUser = '';

        });
    }
}
</script>