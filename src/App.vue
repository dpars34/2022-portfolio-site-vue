<template>
  <div>
    <TitleScreen v-if="isTitleScreenShowing && !isTransitioning" @handle-click="handleTitleScreenClick"/>
    <ToEnglishTransition v-if="isTitleScreenShowing && isTransitioning && isEnglish"/>
    <ToJapaneseTransition v-if="isTitleScreenShowing && isTransitioning && !isEnglish"/>
    <EnglishScreen v-if="!isTitleScreenShowing && !isTransitioning && isEnglish" @handle-click="handleScreenClick"/>
    <JapaneseScreen v-if="!isTitleScreenShowing && !isTransitioning && !isEnglish" @handle-click="handleScreenClick"/>
    <EnglishToJapaneseTransition v-if="!isTitleScreenShowing && isTransitioning && !isEnglish"/>
    <JapaneseToEnglishTransition v-if="!isTitleScreenShowing && isTransitioning && isEnglish"/>
  </div>
</template>

<script>
import TitleScreen from '@/screens/TitleScreen'
import EnglishScreen from '@/screens/EnglishScreen'
import JapaneseScreen from '@/screens/JapaneseScreen'
import ToEnglishTransition from '@/screens/ToEnglishTransition'
import ToJapaneseTransition from '@/screens/ToJapaneseTransition'
import EnglishToJapaneseTransition from '@/screens/EnglishToJapaneseTransition'
import JapaneseToEnglishTransition from '@/screens/JapaneseToEnglishTransition'

export default {
  name: 'App',
  components: {
    TitleScreen,
    EnglishScreen,
    JapaneseScreen,
    ToEnglishTransition,
    ToJapaneseTransition,
    EnglishToJapaneseTransition,
    JapaneseToEnglishTransition,
  },
  data() {
    return {
      isTitleScreenShowing: true,
      isTransitioning: false,
      isEnglish: true,
    }
  },
  methods: {
    handleTitleScreenClick(event) {
      if (event === "english") {
        document.body.style.background = "#232323";
        setTimeout(() => {
          this.isTransitioning = true
          this.isEnglish = true
        }, 500) 
        setTimeout(() => {
          this.isTransitioning = false
          this.isTitleScreenShowing = false
        }, 1500) 
      } 
      
      if (event === "japanese") {
        document.body.style.background = "#ececec";
        setTimeout(() => {
          this.isTransitioning = true
          this.isEnglish = false
        }, 500) 
        setTimeout(() => {
          this.isTransitioning = false
          this.isTitleScreenShowing = false
        }, 1500) 
      }

      if (event === "contact") {
        document.body.style.background = "#232323";
        setTimeout(() => {
          this.isTransitioning = true
          this.isEnglish = true
        }, 500) 
        setTimeout(() => {
          this.isTransitioning = false
          this.isTitleScreenShowing = false
        }, 1500)
      } 
    },

    handleScreenClick(isEnglish) {
      if (isEnglish) {
        setTimeout(() => {
          this.isTransitioning = true
          this.isEnglish = false
        }, 500)
        setTimeout(() => {
          document.body.style.background = "#ececec";
          this.isTransitioning = false
        }, 1500) 

      } else {
        setTimeout(() => {
          this.isTransitioning = true
          this.isEnglish = true
        }, 500)
        setTimeout(() => {
          document.body.style.background = "#232323";
          this.isTransitioning = false
        }, 1500) 
      }
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cabin:ital@0;1&family=M+PLUS+1p&family=Quantico&display=swap');

body {
  background-color: #232323;
}

#app {
  font-family: 'Quantico', 'M PLUS 1p', 'Arial', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #232323;
  padding: 0;
  margin: 0;
}
</style>
