<template>
  <div class="english-screen">
      <Navbar :isEnglish="true" @handle-click="handleClick"/>
      <AboutMe :data="aboutMeData" :isEnglish="true"/>
      <Line />
      <Projects :data="projectsData" :isEnglish="true"/>
      <Line />
      <Contact :data="contactData" :isEnglish="true"/>
      <Footer :isEnglish="true"/>
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
    name: 'English Screen',
    components: { AboutMe, Line, Projects, Contact, Footer, Navbar },
    data() {
        return {
            aboutMeData: data.english.aboutMe,
            projectsData: data.english.projects,
            contactData: data.english.contact
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
.english-screen {
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