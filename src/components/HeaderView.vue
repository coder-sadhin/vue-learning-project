<template>
  <div id="nav " class="mb-3 bg-dark">
    <div class="container">
      <nav class="navbar navbar-expand-lg">
        <div class="container-fluid">
          <router-link class="navbar-brand text-light" to="/">{{
            siteTitle
          }}</router-link>
          <button
            class="navbar-toggler"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#navbarSupportedContent"
            aria-controls="navbarSupportedContent"
            aria-expanded="false"
            aria-label="Toggle navigation"
          >
            <span class="navbar-toggler-icon"></span>
          </button>
          <div
            class="collapse navbar-collapse ml-auto"
            id="navbarSupportedContent"
          >
            <ul class="navbar-nav">
              <li class="nav-item active">
                <router-link class="nav-link text-light" to="/"
                  >Home</router-link
                >
              </li>
              <li class="nav-item">
                <router-link class="nav-link text-light" to="/about"
                  >About</router-link
                >
              </li>
            </ul>
          </div>
        </div>
      </nav>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeaderView",
  data() {
    return {
      siteTitle: "First Title of vue",
    };
  },
};
</script>