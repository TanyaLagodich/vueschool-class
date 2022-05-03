<template>
    <div class="col-full">
        <div class="thread-list">
            <h2 class="list-title">Threads</h2>
            <div
                v-for="thread in threads"
                :key="thread.id"
                class="thread"
            >
                  <div>
                      <p>
                          <a href="#">{{ thread.title }}</a>
                      </p>
                      <p class="text-faded text-xsmall">
                          By <a href="#">{{ userById(thread.userId).name }}</a>, {{ thread.publishedAt }}.
                      </p>
                  </div>

                  <div class="activity">
                      <p class="replies-count">
                          {{ thread.posts.length }}
                      </p>

                      <img class="avatar-medium"
                           src="http://i0.kym-cdn.com/photos/images/facebook/000/010/934/46623-batman_pikachu_super.png"
                           alt="">

                      <div>
                          <p class="text-xsmall">
                              <a href="profile.html">Bruce Wayne</a>
                          </p>
                          <p class="text-xsmall text-faded">2 hours ago</p>
                      </div>
                  </div>
              </div>
        </div>
    </div>
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