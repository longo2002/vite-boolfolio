<template>
    <div class="project-card">
        <h2>{{ project.name }}</h2>
        <p>{{ project.description }}</p>
    </div>
</template>
  
<script>
import vue from vue;

export default {
    props: {
        project: {
            type: Object,
            required: true,
        },
    },
};
</script>
  
<style scoped>
.project-card {
    border: 1px solid #ddd;
    padding: 1rem;
    margin: 1rem;
}
</style>