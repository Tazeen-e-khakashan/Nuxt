<template>
  <div class="container">
    <ul>
      <NuxtLink v-if="page > 1" :to="'?page=' + (page - 1)">
        <button class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-2 px-4 rounded-l">
          &lt; Prev
        </button>
      </NuxtLink>
      <a v-else class="disabled">
        <button class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-2 px-4 rounded-l">
          &lt;  Prev
        </button>
      </a>
      <span>{{ page }}/{{ totalPages }}</span>
      <NuxtLink v-if="page < totalPages" :to="'?page=' + (page + 1)">
        <button class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-2 px-4 rounded-r">
          Next&gt;</button></NuxtLink>
      <a v-else class="disabled">
        <button class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-2 px-4 rounded-r">
          Next&gt;
        </button>
      </a>
      <li v-for="user in users" :key="user.id">
        <img :src="user.avatar" class="avatar">
        <span>{{ user.first_name }} {{ user.last_name }}</span>
      </li>
      <p>
        <NuxtLink to="/">
          Back home
        </NuxtLink>
      </p>
    </ul>
  </div>
</template>

<script>
export default {
  watchQuery: ['page'],
  key: to => to.fullPath,
  transition (to, from) {
    if (!from) { return 'slide-left' }
    return +to.query.page < +from.query.page ? 'slide-right' : 'slide-left'
  },
  async asyncData ({ query }) {
    const page = +query.page || 1
    const data = await fetch(`https://reqres.in/api/users?page=${page}`).then(res => res.json())
    return {
      page: +data.page,
      totalPages: data.total_pages,
      users: data.data
    }
  }
}
</script>
<style scoped>
a {
  display: inline-block;
  margin: 0 1em;
  color: #34495e;
  text-decoration: none;
}
a.disabled {
  color: #ccc;
}
ul {
  margin: auto;
  padding: 0;
  width: 100%;
  max-width: 400px;
  padding-top: 40px;
}
li {
  list-style-type: none;
  width: 400px;
  border: 1px #ddd solid;
  overflow: hidden;
}
li img {
  float: left;
  width: 100px;
  height: 100px;
}
li span {
  display: inline-block;
  padding-top: 40px;
  text-transform: uppercase;
}
</style>