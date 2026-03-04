<template>
  <section class="pb-5 container" id="projects">
    <h1 class="project mt-5 mb-5 pb-4 text-center">My Projects</h1>

    <div
      v-for="(group, index) in chunkedProjects"
      :key="index"
      class="row my-5 justify-content-center"
    >
      <ProjectCard
        v-for="project in group"
        :key="project.id"
        :project="project"
        class="col-md-4 mb-4"
      />
    </div>
  </section>
</template>

<script setup>
import { computed } from "vue";
import ProjectCard from "./ProjectCard.vue";
import projects from "../data/projects.json";

const chunkSize = 3;

const chunkedProjects = computed(() => {
  const chunks = [];
  for (let i = 0; i < projects.length; i += chunkSize) {
    chunks.push(projects.slice(i, i + chunkSize));
  }
  return chunks;
});
</script>

<style scoped>
/* Header Styles */
.project {
  font-family: 'Archivo', sans-serif;
  font-weight: 900;
  font-size: clamp(2rem, 7vw, 2.5rem); 
  margin-top: 5rem;
}

.text-center {
  color: var(--accent-gold); 
  font-size: clamp(2rem, 7vw, 2.5rem);
}

/* Deep Selectors to fix the Child Component (ProjectCard) */
:deep(.project-card-light) {
  background-color: #FFFFFF !important; 
  border-radius: 15px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05); 
  transition: transform 0.3s ease;
  height: 100%; /* Ensures all cards in a row are same height */
  display: flex;
  flex-direction: column;
}

:deep(.project-card-light:hover) {
  transform: translateY(-8px);
}

/* Fixes the Image Stretching */
:deep(.project-card-light .card-img-top) {
  height: 250px;
  object-fit: cover; /* Crops the image instead of stretching it */
  width: 100%;
}

/* Fixes the Button Alignment */
:deep(.card-body) {
  display: flex;
  flex-direction: column;
  flex-grow: 1;
}

:deep(.card-text) {
  flex-grow: 1; /* Pushes the button to the bottom */
}

:deep(.project-card-light h4) {
  font-size: 1.25rem;
  margin-bottom: 15px;
}
</style>