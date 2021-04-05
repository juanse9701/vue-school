<template>
  <h2>Welcome to page Home</h2>
  <div>
    <h3>List Posts</h3>
    <ol>
      <li v-for="post in posts" :key="post.id">
        <div>
          <h4>{{post.title}}</h4>
          <p>{{post.body}}</p>
          <p>User: {{ userById(post.userId).name}}</p>
        </div>
      </li>
    </ol>
  </div>
</template>

<script>
import sourceData from '@/data.json'

export default {
  data () {
    return {
      posts: sourceData.posts,
      users: sourceData.users
    }
  },
  methods: {
    userById (userId) {
      return this.users.find(({ id }) => id === userId)
    }
  }

}
</script>

<style scoped>

</style>
