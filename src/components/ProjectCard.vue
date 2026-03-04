<template>
  <div class="card col-md-3">
    <img :src="project.image" :alt="project.title" class="card-img-top" />
    <div class="card-body">
      <h5 class="card-title">{{ project.title }}</h5>
      <p class="card-text">{{ project.description }}</p>
      
      <a :href="project.link" target="_blank" class="btn btn-primary">
        View Project
      </a>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from "vue"

defineProps({
  project: Object
})
</script>