<template>
  <div>
    <div class="card mb-3" v-for="comment of comments" :key="comment.id">
      <div class="card-body">
        <div class="row g-0">
          <div class="col-md-2">
            <img
              src="@/assets/logo.png"
              class="img-fluid rounded-start"
              alt=""
            />
          </div>
          <div class="col-md-10">
            <div class="card-body">
              <h5 class="card-title">{{ comment.name }}</h5>
              <p class="card-text">
                {{ comment.body }}
              </p>
              <p class="card-text">
                <small class="text-muted">{{ comment.email }}</small>
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "PostComments",
  data() {
    return {
      id: this.$route.params.id,
      comments: [],
    };
  },
  created() {
    axios
      .get(`https://jsonplaceholder.typicode.com/comments?postId=${this.id}`)
      .then((res) => {
        this.comments = res.data;
      })
      .catch((e) => {
        this.error.push(e);
      });
  },
};
</script>

<style>
</style>