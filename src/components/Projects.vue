<template>


<!--  My Projects -->
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
            class="col-md-4"
          />
        </div>
    </section>
</template>

<script setup>
    
import { computed } from "vue"; // import computed for dynamic calculated state

import ProjectCard from "./ProjectCard.vue"; // import ProjectCard component
import projects from "../data/projects.json"; // import projects data

const chunkSize = 3; // number of projects per row

// compute projects in chunks of 3
const chunkedProjects = computed(() => {
    const chunks = [] // array to store project groups

    for (let i = 0; i < projects.length; i += chunkSize) {
        chunks.push(projects.slice(i, i + chunkSize)) // take 3 projects at a time
    }

    return chunks // return grouped projects
})
</script>

<style scoped>

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

.projects-section {
    background-color: var(--secondary-bg) !important; 
    padding: 80px 0;
}

.project-card-light {
    background-color: #FFFFFF !important; 
    border-radius: 15px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05); 
    transition: transform 0.3s ease;
}

.project-card-light:hover {
    transform: translateY(-8px);
}

.project-card-light .card-img-top {
    height: 250px;
    object-fit: cover; /* Crops the image to fit without stretching */
    width: 100%;
}

.project-card-light h4 {
    font-size: 1.25rem;
    margin-bottom: 15px;
}

</style> 