<template>
  <div class="card my-3">
    <div class="card-body">
      <h3>{{ post.title }}</h3>
      <p>{{ post.body }}</p>
    </div>
  </div>
  <PostComments />
</template>
  
  <script>
import axios from "axios";
import PostComments from "@/views/PostComments.vue";

export default {
  name: "PostDetails",
  components: {
    PostComments,
  },
  data() {
    return {
      id: this.$route.params.id,
      post: [],
      error: [],
    };
  },
  created() {
    axios
      .get(`https://jsonplaceholder.typicode.com/posts/${this.id}`)
      .then((res) => {
        this.post = res.data;
      })
      .catch((e) => {
        this.error.push(e);
      });
  },
};
</script>
  
  <style scoped>
</style>