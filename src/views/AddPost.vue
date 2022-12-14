<template>
  <div class="row mb-3">
    <div class="col text-right">
      <button class="btn btn-primary" v-on:click="formShow">Add Post</button>
    </div>
  </div>
  <div class="bg-dark my-3" v-if="formDiv">
    <div class="card">
      <div class="card-body">
        <form action="" @submit.prevent="addPost">
          <div class="form-group">
            <label>Post Title</label>
            <input
              type="text"
              name="title"
              v-model="title"
              placeholder="Enter Post Title Here"
              class="form-control"
            />
          </div>
          <div class="form-group">
            <label>Post Details</label>
            <textarea
              name="body"
              v-model="body"
              placeholder="Enter Post Details"
              class="form-control"
            ></textarea>
          </div>
          <div class="row mt-3">
            <div class="d-grid gap-2 col-6 mx-auto">
              <button class="btn btn-block btn-success" type="submit">
                Create Post
              </button>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>
  
  <script>
export default {
  name: "AddPost",
  data() {
    return {
      formDiv: false,
      title: "",
      body: "",
    };
  },
  methods: {
    formShow() {
      this.formDiv = true;
    },
    // 35 job( UAE, USA,UK,India,Vietnam)
    addPost() {
      const newPost = {
        title: this.title,
        body: this.body,
      };

      // send to parent
      this.$emit("add-post", newPost);
      (this.title = ""), (this.body = "");
    },
  },
};
</script>
  
  <style scoped>
</style>