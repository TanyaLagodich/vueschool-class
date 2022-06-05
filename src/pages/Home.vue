<template>
  <h1>Welcome to the Forum!</h1>
  <category-list :categories="categories" />
</template>
<script>
import categoryList from '@/components/CategoryList'

export default {
  components: {
    categoryList
  },
  computed: {
    categories () {
      return this.$store.state.categories
    }
  }
}
</script>
