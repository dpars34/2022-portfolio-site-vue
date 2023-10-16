<template>
  <div class="title-screen">
    <div class="flex-container" :class="{'flex-container-fade-out': textFadeOut}">
        <p class="name-title"><span class="daniel-text">Daniel</span><span class="parsons-text">Parsons</span></p>
        <p class="subtitle"><span class="bilingual-text">Bilingual</span><span class="developer-text">Developer</span></p>
        <img class="profile-picture" src="../assets/profile_image.jpeg" alt="Daniel Parsons profile">
        <div class="bottom-area">
            <div class="english-button" @click="handleClickEnglish">
                <div class="svg-container">
                    <svg width="100%" height="100%" viewBox="0 0 72 72" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M46.2299 22.23L32.4899 36L46.2299 49.77L41.9999 54L23.9999 36L41.9999 18L46.2299 22.23Z" fill="#e1e1e1"/>
                    </svg>
                </div>
                <p class="english-language-label">English</p>
            </div>
            <!-- <Button text="Contact" class="contact-button" @click="handleClickContact"/> -->
            <div class="japanese-button" @click="handleClickJapanese">
                <p class="japanese-language-label">日本語</p>
                <div class="svg-container">
                    <svg width="100%" height="100%" viewBox="0 0 72 72" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M25.7701 49.77L39.5101 36L25.7701 22.23L30.0001 18L48.0001 36L30.0001 54L25.7701 49.77Z" fill="#232323"/>
                    </svg>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
// import Button from '@/components/Button'

export default {
    name: "TitleScreen",
    // components: { Button },
    data() {
        return {
            textFadeOut: false
        }
    },
    methods: {
        handleClickEnglish() {
            this.textFadeOut = true
            this.$emit('handle-click', 'english')
        },
        handleClickJapanese() {
            this.textFadeOut = true
            this.$emit('handle-click', 'japanese')
        },
        handleClickContact() {
            this.textFadeOut = true
            this.$emit('handle-click', 'contact')
        }
    }
}
</script>

<style scoped>

.title-screen{
    min-height: 100vh;
    width: 100vw;
    background-image: linear-gradient(88deg, #232323 49.8%, #ececec 49.9%);
    font-family: 'Cabin', sans-serif;
    background-size: 250%;
    background-position: 50% 50%;
    display: flex;
    align-items: center;
}

.flex-container{
    height: 100%;
    width: 100%;
    padding: 3rem 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.flex-container-fade-out {
    animation: fade-out 0.5s forwards;
}

@keyframes fade-out {
    from {
        opacity: 1;
    }
    to {
        opacity: 0;
    }
}

.name-title {
    font-size: 5rem;
    padding: 0;
    margin: 0;
}

.subtitle {
    font-size: 2.4rem;
    margin: 0;
}

.daniel-text {
    color: #e1e1e1;
    padding-right: 2rem;
}

.bilingual-text {
    color: #e1e1e1;
    padding-right: 2rem;
}

.profile-picture {
    height: 20rem;
    margin-top: 5rem;
    border-radius: 50%;
    box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
    filter: grayscale(100%);
}

.bottom-area {
    display: flex;
    width: 100vw;
    max-width: 1440px;
    padding-top: 5rem;
    justify-content: space-evenly;
    align-items: center;
}

.contact-button {
    display: none;
}

.english-button {
    font-size: 3rem;
    color: #e1e1e1;
    display: flex;
    align-items: center;
}

.english-button:hover > .svg-container {
    animation: move-left 0.5s forwards;
}

@keyframes move-left {
    from {
        transform: translate(0)
    }

    to {
        transform: translate(-1rem)
    }
}

.japanese-button {
    font-size: 3rem;
    color: #232323;
    display: flex;
    align-items: center;
}

.japanese-button:hover > .svg-container {
    animation: move-right 0.5s forwards;
}

@keyframes move-right {
    from {
        transform: translate(0)
    }

    to {
        transform: translate(1rem)
    }
}

.english-button:hover, .japanese-button:hover {
    cursor: pointer;
}

.english-language-label {
    margin: 0;
    line-height: 1.3;
}

.japanese-language-label {
    margin: 0;
    line-height: 1;
}

.svg-container {
    height: 6rem;
    width: 6rem;
}

@media screen and (min-width: 768px) {
    .contact-button {
        display: block;
        margin: 3rem;
        font-size: 4rem;
    }

    .contact-button:hover {
        animation: zoom-in 0.5s forwards;
    }

    @keyframes zoom-in {
        from {
            transform: scale(1)
        }

        to {
            transform: scale(1.1)
        }
    }

    .name-title {
        font-size: 7.2rem;
    }

    .subtitle {
        font-size: 3.2rem;
    }   

    .profile-picture {
        height: 25rem;
    }

    .english-button {
        font-size: 4rem;
    }

    .japanese-button {
        font-size: 4rem;
    }

    .svg-container {
        height: 7.2rem;
        width: 7.2rem;
    }

}
</style>