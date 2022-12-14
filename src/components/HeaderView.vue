<template>
  <nav class="navbar navbar-expand-lg bg-light">
  <div class="container-fluid">
    <router-link class="navbar-brand" to="/">Practics Project</router-link>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <router-link class="nav-link" to="/">Home</router-link>
        </li>
        <li class="nav-item">
            <router-link class="nav-link" to="/about">About</router-link>
        </li>
      </ul>
    </div>
  </div>
</nav>
  <!-- <div class="hello">
    hell
  </div> -->
  <nav>
     
    
  </nav>
</template>

<script>
export default {
  name: "HeaderView"
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
