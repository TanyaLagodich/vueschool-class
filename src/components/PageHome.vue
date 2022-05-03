<template>
  <h1>Welcome to the Forum!</h1>
  <thread-list :threads="threads" />
</template>
<script>
import sourceData from '@/data.json'

export default {
  data () {
    return {
      threads: sourceData.threads,
      posts: sourceData.posts,
      users: sourceData.users
    }
  },
  methods: {
    postById (postId) {
      return this.posts.find((p) => p.id === postId)
    },
    userById (userId) {
      return this.users.find((u) => u.id === userId)
    }
  }
}
</script>
