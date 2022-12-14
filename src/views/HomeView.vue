<template>
  <div class="home">
    <AddPost />
    <PostList v-bind:posts="posts" :errors="errors" />
  </div>
</template>

<script>
// @ is an alias to /src

import AddPost from "./AddPost.vue";
import PostList from "./PostList.vue";
import axios from "axios";

export default {
  name: "HomeView",
  components: {
    AddPost,
    PostList,
  },
  data() {
    return {
      posts: [],
      errors: [],
    };
  },
  created() {
    axios
      .get(`https://jsonplaceholder.typicode.com/posts?_limit=10`)
      .then((res) => {
        this.posts = res.data;
      })
      .catch((e) => {
        this.errors.push(e);
      });
  },
};
</script>
