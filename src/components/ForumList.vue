<template>
  <div class="col-full">
      <div class="forum-list">
        <h2 class="list-title">Forums</h2>

        <div
            class="forum-listing"
            v-for="forum in forums"
            :key="forum.id"
            >
        <div class="forum-details">
            <router-link
            class="forum-name"
            :to="{ name: 'Forum', params: { id: forum.id } }"
            >
            {{ forum.name }}
            </router-link>
            <p class="forum-description ">{{ forum.description }}</p>
        </div>
        <div class="threads-count">
            <p class="count text-lead">{{ forum.threads?.length }}</p>
            {{ forumThreadWord(forum) }}
        </div>
        <div class="last-thread">
        </div>
        </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    forums: {
      type: Array,
      required: true
    }
  },
  methods: {
    forumThreadWord (forum) {
      if (forum.threads?.length) {
        if (forum.threads.length > 1) return 'threads'
        return 'thread'
      }
      return 'no threads'
    }
  }
}
</script>
