<template>
  <div>
    <form
        class="form"
        @submit.prevent
    >
      <h4>Создание поста</h4>

      <my-input
          v-model="post.title"
          placeholder="Название"
      />

      <my-input
          v-model="post.body"
          placeholder="Описание"/>

      <my-button

          @click="createPost"
      >Создать
      </my-button>
    </form>
  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton";
import MyInput from "@/components/UI/MyInput";
export default {
  components: {MyInput, MyButton},
  data() {
    return {
      post: {
        title: '',
        body: ''
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now()
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: ''
      }
    }
  }

}
</script>

<style scoped>

.form {
  display: flex;
  flex-direction: column;

}




</style>