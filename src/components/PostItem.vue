<template>
  <div>
    <div class="post">
      <div><strong>Название:</strong> {{ post.title }}</div>
      <div><strong>Название:</strong> {{ post.body }}</div>
    </div>
    <div class="post__btn">
      <my-button
          @click="$emit('remove', post)"
      >
        Удалить
      </my-button>
    </div>
  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton";
console.log('')
export default {
  components: {MyButton},
  props: {
    post: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>

</style>