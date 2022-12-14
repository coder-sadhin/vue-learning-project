<template>
  <div class="home">
    <AddPost v-on:add-post="addPostForm" />
    <PostList v-on:del-post="delPost" v-bind:posts="posts" :errors="errors" />
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
  methods: {
    addPostForm(newPost) {
      const { title, body } = newPost;
      axios
        .post("https://jsonplaceholder.typicode.com/posts", {
          title,
          body,
        })
        .then((res) => (this.posts = [...this.posts, res.data]))
        .catch((err) => console.log(err));
    },
    delPost(id) {
      axios
        .delete(`https://jsonplaceholder.typicode.com/posts/${id}`)
        .then((res) => {
          console.log(res);
          this.posts = this.posts.filter((post) => post.id !== id);
        })
        .catch((err) => console.log(err));
    },
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

