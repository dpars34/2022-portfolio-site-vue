<template>
  <div class="projects">
      <Header :text="data.title" :isEnglish="isEnglish"/>
        <div class="projects__card-container">
            <div class="projects__card" v-for="(project, index) in data.projects" :key="index">
                <Card :data="project" :isEnglish="isEnglish"/>
            </div>
        </div>
  </div>
</template>

<script>
import Header from "@/components/Header"
import Card from '@/components/Card'

export default {
    name: 'Projects',
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

<style scoped>
.projects {
    padding: 3.2rem 1.6rem;
    max-width: calc(1440px - 20rem);
    margin: auto;
}

 .projects__card-container {
    display: flex;
    flex-direction: column;
    gap: 4.8rem;
    margin-top: 1.6rem;
 }

.projects__card:last-child {
    margin: 0;
}

@media screen and (min-width: 768px) {
  .projects {
    padding: 3.2rem 10rem;
  }

  .projects__card-container {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
      margin: 3.2rem 0;
  }

  .projects__card {
      display: flex;
  }
}
</style>