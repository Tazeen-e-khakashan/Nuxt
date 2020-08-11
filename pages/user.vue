<template>
    <div class="container">
        <table class="table-auto mx-8 my-6 items-center justify-center">
             <p v-if="submitting">Submitting...</p>
             <p v-if="loading">Loading...</p>
            <thead>
                <tr>
                    <th  class="px-4 py-2">Id</th>
                    <th  class="px-4 py-2">Task</th>
                    <th  class="px-4 py-2">Action</th>

                </tr>
            </thead>
            <tbody class="bg-gray-300">
                <tr  v-for="user in users" :key="user.id">
                    <td class="border px-4 py-2">{{ user.id }}</td>
                    <td class="border px-4 py-2">
                        <span v-if="!user.isEdit">{{user.name}}</span>
                        <span v-if="user.isEdit"><input type="text" placeholder="user name" v-model="user.name"></span>
                    </td>
                    <td class="border px-4 py-2">
                        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="showEditInput(user)" @on-enter="saveTask(user)">Edit</button>
                        <button class="bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-4 rounded">Delete</button>
 </td>
                </tr>
            </tbody>

        </table>
    </div>
</template>
<script>
export default {
    data(){
        return {

      loading: false,
      submitting: false,
      newUser: '',
    };
    },
    asyncData ({$axios}){
        return $axios.get('https://jsonplaceholder.typicode.com/users')
        .then(response =>{
             return{users:response.data}
        })
        return $axios.push('https://jsonplaceholder.typicode.com/users')
        .then (response => {
            return{user:thisnewUser}
        });

    },
    methods : {
        showEditInput(user){
            this.$set(user, 'isEdit', true)

        },
        // saveTask(user){
        //     user.isEdit = false
        // },
       saveTask() {
       this.submitting = true;

        const data = response.data;
         this.user.push(data);
         this.newUser = '';
         this.submitting = false;

    }

    }


}
</script>