<template>
  <div>
    <TitleScreen v-if="titleScreenShowing"/>
    <EnglishScreen v-if="!titleScreenShowing && isEnglish" />
    <JapaneseScreen v-if="!titleScreenShowing && !isEnglish"/>
  </div>
</template>

<script>
import TitleScreen from '@/screens/TitleScreen'
import EnglishScreen from '@/screens/EnglishScreen'
import JapaneseScreen from '@/screens/JapaneseScreen'

export default {
  name: 'App',
  components: {
    TitleScreen,
    EnglishScreen,
    JapaneseScreen
  },
  data() {
    return {
      titleScreenShowing: true,
      isEnglish: true
    }
  }
}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Cabin:ital@0;1&family=M+PLUS+1p&family=Quantico&display=swap');

html {
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
