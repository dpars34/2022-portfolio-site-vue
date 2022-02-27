<template>
  <div class="english-screen">
      <Navbar :isEnglish="true" @handle-click="handleClick"/>
      <div :class="fadeOut ? 'english-screen-fade-out' : 'english-screen-content'">
        <AboutMe :data="aboutMeData" :isEnglish="true"/>
        <Line />
        <Projects :data="projectsData" :isEnglish="true"/>
        <Line />
        <Contact :data="contactData" :isEnglish="true"/>
        <Footer :isEnglish="true"/>
      </div>
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
            contactData: data.english.contact,
            fadeOut: false
        }
    },
    methods: {
        handleClick(isEnglish) {
            this.fadeOut = true
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

.english-screen-fade-out {
    animation: fade-out 0.5s forwards;
}

@keyframes fade-out {
    from {
        opacity: 1
    }
    to {
        opacity: 0
    }
}
</style>