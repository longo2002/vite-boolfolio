<template>
  <div class="app">
    <h1>Progetti</h1>
    <div v-if="loading">Caricamento...</div>
    <div v-else>
      <project-card v-for="project in projects" :key="project.id" :project="project" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import ProjectCard from "./components/ProjectCard.vue";

export default {
  components: {
    ProjectCard,
  },
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
