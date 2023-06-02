<template>
  <div v-if="posts.length > 0">
    <h3>Список пользователей</h3>
    <post-item
        class="post"
        v-for="post in posts"
        :post="post"
        :key="post.id"
        @remove="$emit('remove', post)"
    />
  </div>
  <h2 v-else="posts.length === 0">
    Список пользователей пуст
  </h2>
</template>

<script>
import PostItem from "@/components/PostItem";
console.log('')
export default {
  components: {PostItem},
  props: {
    posts: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>

.post {
  padding: 15px;
  border: 1px solid teal;
  margin: 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

</style>