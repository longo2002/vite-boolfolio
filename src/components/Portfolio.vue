<template>
    <div>
        <h1>Portfolio</h1>
        <ProjectCard v-for="(project, index) in projects" :key="index" :project="project" />
    </div>
</template>
  
<script>
import ProjectCard from '../components/ProjectCard.vue';
import axios from 'axios';

export default {
    name: 'Portfolio',
    components: {
        ProjectCard
    },
    data() {
        return {
            projects: []
        };
    },
    mounted() {
        axios.get('http://localhost:8000/api/projects')
            .then(response => {
                this.projects = response.data;
            })
            .catch(error => {
                console.log(error);
            });
    }
};
</script>