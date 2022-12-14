<template>
  <HeaderView />
  <div class="container text-light">
    <router-view />
  </div>
</template>

<script>
import HeaderView from "@/components/HeaderView.vue";
export default {
  components: {
    HeaderView,
  },
};
</script>

<style>
body {
  background: #222831;
}
.container {
  max-width: 900px;
}
.card {
  background: #1a1d24;
}
.card-body {
  color: #f9ffee;
}
.card-body a {
  color: #efbb35;
}
</style>
