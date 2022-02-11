<template>
  <div class="projects">
      <Header :text="data.title" :isEnglish="isEnglish"/>
        <div class="projects__card" v-for="(project, index) in data.projects" :key="index">
            <Card :data="project" :isEnglish="isEnglish"/>
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
    padding: 3.2rem 1.6rem;
}

.projects__card {
    margin: 4.8rem 0;
}

.projects__card:last-child {
    margin: 0;
}
</style>