<template>
  <div class="english-screen">
      <AboutMe :data="aboutMeData" :isEnglish="true"/>
      <Line />
  </div>
</template>

<script>
import data from '@/data.json'
import AboutMe from '@/components/AboutMe'
import Line from '@/components/Line'
export default {
    name: 'English Screen',
    components: { AboutMe, Line },
    data() {
        return {
            aboutMeData: data.english.aboutMe,
            projectsData: data.english.projects,
            contactData: data.english.contact
        }
    }
}
</script>

<style>

</style>