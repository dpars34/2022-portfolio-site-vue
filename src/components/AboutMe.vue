<template>
  <div class="about-me">
      <Header :text="data.title" :isEnglish="isEnglish"/>
      <div class="about-me__text-section" v-for="(section, index) in data.text" :key="index">
          <p class="about-me__text" :class="{ 'about-me__japanese': !isEnglish }">{{ section }}</p>
      </div>
  </div>
</template>

<script>
import Header from "@/components/Header"
export default {
    name: "AboutMe",
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
    components: { Header }
}
</script>

<style>
.about-me {
    padding: 3.2rem 1.6rem;
}
.about-me__text {
    font-size: 1.6rem;
    color: #e1e1e1;
}

.about-me__japanese {
    color: #232323;
    line-height: 1.7;
}

</style>