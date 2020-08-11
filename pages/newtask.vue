<template>
 <div id="app-vue">
      <div class="users">
        <button class="btn btn-primary" @click="fetchUsers">
          Fetch Users
        </button>

        <input
          class="add-search-input"
          type="text"
          v-model="newUser"
          @keyup.enter="addUser"
        >

        <div>
          <p v-if="submitting">Submitting...</p>
          <!-- <p v-if="loading">Loading...</p> -->

          <ul>
            <li v-for="user in users" :key="user">
              {{ user.name }} - {{ user.id }}
            </li>
          </ul>
        </div>
      </div>
    </div>

</template>
<script>
export default {
    data() {
    return {
      users: [],
    //   loading: false,
      submitting: false,
      newUser: '',
    }
  },
  async ({$axios})  {

         return  $axios.get('https://jsonplaceholder.typicode.com/users')
        .then((response) => {
          const data = response.data;
          this.users = data;
        //   this.loading = false;
        });

      },
  methods: {
    fetchUsers() {
      this.loading = true;
      this.users = [];

    //     async ({$axios}) => {

    //      return  $axios.get('https://jsonplaceholder.typicode.com/users')
    //     .then((response) => {
    //       const data = response.data;
    //       this.users = data;
    //       this.loading = false;
    //     });

    //   };
    },
    addUser() {
      this.submitting = true;
      async ({axios}) =>{
         return $axios.post('https://jsonplaceholder.typicode.com/users', {
        name: this.newUser
      })
        .then((response) => {
          const data = response.data;
          this.users.push(data);
          this.newUser = '';
          this.submitting = false;
        });

      }

    }
  }
}
</script>
<style>
#app-vue {
  display: flex;
  justify-content: center;
}

.users {
  width: 300px;
  border: 1px solid black;
  display: flex;
  flex-direction: column;
  padding: 20px;
  background: #FFEEE4;
}

.add-search-input {
  margin-top: 10px;
}

li {
  margin: 20px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

</style>