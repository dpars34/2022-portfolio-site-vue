<template>
  <div class="japanese-screen">
      <AboutMe :data="aboutMeData" :isEnglish="false"/>
      <Line />
      <Projects :data="projectsData" :isEnglish="false"/>
      <Line />
      <Contact :data="contactData" :isEnglish="false"/>
  </div>
</template>

<script>
import data from '@/data.json'
import AboutMe from '@/components/AboutMe'
import Line from '@/components/Line'
import Projects from '@/components/Projects'
import Contact from '@/components/Contact'

export default {
    name: 'Japanese Screen',
    components: { AboutMe, Line, Projects, Contact },
    data() {
        return {
            aboutMeData: data.japanese.aboutMe,
            projectsData: data.japanese.projects,
            contactData: data.japanese.contact
        }
    }
}
</script>

<style>
.japanese-screen {
  background-color: #ececec;
}
</style>