<template>
  <div class="app">
    <post-form
        @create="createPost"
    />
    <post-list
        v-bind:posts="posts"
        @remove="removePost"
    />
  </div>
</template>

<script>
import PostList from "@/components/PostList";
import PostForm from "@/components/PostForm";

export default {
  components: {
    PostForm,
    PostList
  },
  data() {
    return {
      posts: [
        {id: 1, title: 'Javascript', body: 'Описание поста'},
        {id: 2, title: 'Javascript 2', body: 'Описание поста 2'},
        {id: 3, title: 'Javascript 3', body: 'Описание поста 3'},
        {id: 4, title: 'Javascript 4', body: 'Описание поста 4'},
      ],
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
    },
    removePost(post){
      this.posts = this.posts.filter(p => p.id !== post.id)
    }
  }
}

</script>


<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}


</style>