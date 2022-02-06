<template>
  <div class="projects">
      <Header :text="data.title"/>
      <div class="projects__cards-container" v-for="(project, index) in data.projects" :key="index">
          <div class="projects__card">
            <Card :data="project" />
          </div>
      </div>
  </div>
</template>

<script>
import Header from "@/components/Header"
import Card from '@/components/Card'

export default {
    name: "Projects",
    props: {
        data: {
            type: Object,
            required: true
        },
        isEnglish: {
            type: Boolean,
            default: true
        }
    },
    components: { Header, Card }
}
</script>

<style>
.projects {
    padding: 1.6rem;
}

.projects__card {
    margin: 4.8rem 0;
}
</style>