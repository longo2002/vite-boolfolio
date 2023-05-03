<template>
  <div class="app">
    <h1>Progetti</h1>
    <div v-if="loading">Caricamento...</div>
    <div v-else>
      <div v-for="project in projects" :key="project.id">
        <h2>{{ project.name }}</h2>
        <p>{{ project.description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      projects: [],
      loading: true,
    };
  },
  async created() {
    try {
      const response = await axios.get("http://localhost:8000/api/projects");
      this.projects = response.data;
      this.loading = false;
    } catch (error) {
      console.error(error);
    }
  },
};
</script>
