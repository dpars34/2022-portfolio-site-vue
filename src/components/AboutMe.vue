<template>
  <div class="about-me">
        <Header :text="data.title" :isEnglish="isEnglish"/>
        <div class="about-me__body">
            <div class="about-me__text">
                <div class="about-me__text-section" v-for="(section, index) in data.text" :key="index">
                    <p class="about-me__text" :class="{ 'about-me__japanese': !isEnglish }">{{ section }}</p>
                </div>
            </div>
            <img class="about-me__profile-picture" src="../assets/profile_image.jpeg" alt="Daniel Parsons profile">
        </div>
    </div>
</template>

<script>
import Header from "@/components/Header"
export default {
    name: 'AboutMe',
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

<style scoped>
.about-me {
    padding: 6rem 1.6rem 3.2rem;
    max-width: calc(1440px - 20rem);
    margin: auto;
}

.about-me__text {
    font-size: 1.6rem;
    color: #e1e1e1;
}

.about-me__profile-picture {
    display: none;
}

.about-me__japanese {
    color: #232323;
    line-height: 1.7;
}

@media screen and (min-width: 768px) {
    .about-me { 
        padding: 3.2rem 10rem;
    }

    .about-me__body {
        display: flex;
        align-items: center;
        gap: 5rem;
    }
}

@media screen and (min-width: 1024px) {
    .about-me__profile-picture {
        display: block;
        height: 35rem;
        border-radius: 50%;
        box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
    }
}

</style>