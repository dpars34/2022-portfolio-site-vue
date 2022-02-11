<template>
  <div class="title-screen">
    <div class="flex-container">
        <p class="name-title"><span class="daniel-text">Daniel</span><span class="parsons-text">Parsons</span></p>
        <p class="subtitle"><span class="bilingual-text">Bilingual</span><span class="developer-text">Developer</span></p>
        <img class="profile-picture" src="../assets/profile_image.jpeg" alt="Daniel Parsons profile">
        <div class="bottom-area">
            <div class="english-button">
                <p class="english-language-label">English</p>
                <svg style="width:30px;height:30px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M7.41,8.58L12,13.17L16.59,8.58L18,10L12,16L6,10L7.41,8.58Z" />
                </svg>
            </div>
            <Button text="Contact" class="contact-button" />
            <div class="japanese-button">
                <p class="japanese-language-label">日本語</p>
                <svg style="width:30px;height:30px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M7.41,8.58L12,13.17L16.59,8.58L18,10L12,16L6,10L7.41,8.58Z" />
                </svg>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
import Button from '@/components/Button'

export default {
    name: "TitleScreen",
    components: { Button }
}
</script>

<style scoped>

.title-screen{
    height: 100vh;
    width: 100vw;
    background-image: linear-gradient(88deg, #232323 49.5%, #E1E1E1 49.6%);
    font-family: 'Cabin', sans-serif;
}

.flex-container{
    height: 100%;
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.name-title {
    font-size: 7.2rem;
    padding: 0;
    margin: 0;
}

.subtitle {
    font-size: 2.4rem;
}

.daniel-text {
    color: #FFF;
    padding-right: 3rem;
}

.bilingual-text {
    color: #FFF;
    padding-right: 3rem;
}

.developer-text {
    padding-right: 1rem;
}

.profile-picture {
    max-height: 350px;
    margin-top: 3rem;
    border-radius: 50%;
    box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
}

.bottom-area {
    display: flex;
    width: 100vw;
    justify-content: space-evenly;
    align-items: center;
}

.contact-button {
    margin: 3rem;
    font-size: 3rem;
}

.english-button {
    font-size: 3rem;
    color: #FFFFFF;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.japanese-button {
    font-size: 3rem;
    color: #232323;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.english-language-label {
    margin: 0;
    line-height: 1.3;
}

.japanese-language-label {
    margin: 0;
    line-height: 1;
}

</style>