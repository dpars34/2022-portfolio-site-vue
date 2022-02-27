<template>
  <div class="japanese-screen">
      <Navbar :isEnglish="false" @handle-click="handleClick"/>
      <AboutMe :data="aboutMeData" :isEnglish="false"/>
      <Line />
      <Projects :data="projectsData" :isEnglish="false"/>
      <Line />
      <Contact :data="contactData" :isEnglish="false"/>
      <Footer :isEnglish="false"/>
  </div>
</template>

<script>
import data from '@/data.json'
import Navbar from '@/components/Navbar'
import AboutMe from '@/components/AboutMe'
import Line from '@/components/Line'
import Projects from '@/components/Projects'
import Contact from '@/components/Contact'
import Footer from '@/components/Footer'

export default {
    name: 'Japanese Screen',
    components: { AboutMe, Line, Projects, Contact, Footer, Navbar},
    data() {
        return {
            aboutMeData: data.japanese.aboutMe,
            projectsData: data.japanese.projects,
            contactData: data.japanese.contact
        }
    },
    methods: {
        handleClick(isEnglish) {
            this.$emit('handle-click', isEnglish)
        }
    }
}
</script>

<style>
.japanese-screen {
  background-color: #ececec;
  animation: fade-in 1s forwards;
}

@keyframes fade-in {
    from {
        opacity: 0
    }
    to {
        opacity: 1
    }
}
</style>