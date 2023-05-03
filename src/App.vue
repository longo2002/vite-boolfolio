<template>
  <div class="container">
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
    <router-link to="/portfolio">Portfolio</router-link>
  </div>
  <router-view></router-view>
</template>

<script>

</script>

<style scoped>
.container {
  display: flex;
  gap: 5px;
}
</style>