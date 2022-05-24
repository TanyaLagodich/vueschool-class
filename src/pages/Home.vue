<template>
  <h1>Welcome to the Forum!</h1>
  <forum-list :forums="forums" />
</template>
<script>
import sourceData from '@/data.json'
import ForumList from '@/components/ForumList'

export default {
  components: {
    ForumList
  },
  data () {
    return {
      forums: sourceData.forums
    }
  }
}
</script>
