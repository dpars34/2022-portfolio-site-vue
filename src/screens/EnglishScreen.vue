<template>
  <div class="english-screen">
      <AboutMe :data="aboutMeData" :isEnglish="true"/>
      <Line />
      <Projects :data="projectsData" :isEnglish="true"/>
      <Line />
      <Contact :data="contactData" :isEnglish="true"/>
  </div>
</template>

<script>
import data from '@/data.json'
import AboutMe from '@/components/AboutMe'
import Line from '@/components/Line'
import Projects from '@/components/Projects'
import Contact from '@/components/Contact'

export default {
    name: 'English Screen',
    components: { AboutMe, Line, Projects, Contact },
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