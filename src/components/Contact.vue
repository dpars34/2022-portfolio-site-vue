<template>
  <div id="contact" class="contact">
      <Header :text="data.title" :isEnglish="isEnglish"/>
      <div class="contact__form-container">
          <form ref="form" @submit.prevent="sendEmail">
                <div class="contact__name-email-container">  
                    <div class="contact__form-group">
                        <label class="contact__label" :class="{ 'contact__japanese-text': !isEnglish }" for="user_nam">{{ data.name }}</label>
                        <input class="contact__input" :class="{ 'contact__japanese-input': !isEnglish }" name="user_name" type="text" autocomplete="off" required>
                    </div>
                    <div class="contact__form-group">
                        <label class="contact__label" :class="{ 'contact__japanese-text': !isEnglish }" for="user_email">{{ data.email }}</label>
                        <input class="contact__input" :class="{ 'contact__japanese-input': !isEnglish }" name="user_email" type="text" autocomplete="off" required>
                    </div>
                </div>
                <div class="contact__form-group">
                    <label class="contact__label" :class="{ 'contact__japanese-text': !isEnglish }" for="message">{{ data.message }}</label>
                    <textarea class="contact__textarea" :class="{ 'contact__japanese-input': !isEnglish }" name="message" type="text" autocomplete="off" required></textarea>
                </div>
                <div class="contact__button-container">
                    <input class="contact__button" type="submit" :value="data.send">
                </div>
            </form>
        </div>
    </div>
</template>

<script>
import Header from '@/components/Header'
import emailjs from '@emailjs/browser'
export default {
    name: 'Contact',
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
    components: { Header },
    methods: {
        sendEmail() {
            emailjs.sendForm("service_oecmsbq", "template_bjgamid", this.$refs.form, "user_9EtEh0xOJ964JtXdN23UQ")
            .then((result) => {
                console.log(result.text)
                alert(this.isEnglish ? "Message sent successfully!" : "メッセージが送信されました。")

                const inputs = document.getElementsByClassName('contact__input')
                for (let i = 0; i < inputs.length; i++) {
                    inputs[i].value = ''
                }
                const textArea = document.getElementsByClassName('contact__textarea')
                textArea[0].value = ''

            }, (error) => {
                console.log(error.text)
                alert(this.isEnglish ? "Message could not be sent! " : "メッセージが送信されませんでした。 ");
            })
        },
    }
}
</script>

<style scoped>
.contact {
    padding: 3.2rem 1.6rem;
    max-width: calc(1440px - 20rem);
    margin: auto;
}
.contact__form-group {
    display: flex;
    flex-direction: column;
    margin: 1.6rem 0;
}
.contact__label {
    color: #e1e1e1;
    font-size: 1.6rem;
    margin-bottom: 0.4rem;
}
.contact__input {
    padding: 0.8rem;
    background-color: #232323;
    border: solid 0.1rem #e1e1e1;
    border-radius: 10px;
    color: #e1e1e1;
    font: inherit;
    font-size: 1.6rem;
}
.contact__textarea {
    padding: 0.8rem;
    height: 10rem;
    resize: none;
    background-color: #232323;
    border: solid 0.1rem #e1e1e1;
    border-radius: 10px;
    color: #e1e1e1;
    font: inherit;
    font-size: 1.6rem;
}

.contact__button-container {
    width: 100%;
    display: flex;
    justify-content: center;
    padding-top: 0.8rem;
    font-family: 'Cabin', sans-serif;
    font-size: 2.5rem;
}

.contact__button {
    all: unset;
    padding: 0.1em 1.5em;
    color: #F9F9F9;
    background-color: #DB9205;
    border-radius: 10px;
}

.contact__japanese-text {
    color: #232323;
}

.contact__japanese-input {
    background-color: #F9F9F9;
    border: solid 0.1rem #e1e1e1;
    color: #232323;
}

@media screen and (min-width: 768px) {
    .contact {
        padding: 3.2rem 10rem;
    }

    .contact__name-email-container {
        display: flex;
        gap: 3.2rem;
    }

    .contact__form-group {
        flex: 1;
    }

    .contact__button-container {
        padding-bottom: 0.8rem;
    }

    .contact__button:hover {
        animation: zoom-in 0.5s forwards;
        cursor: pointer;
    }
}

 @keyframes zoom-in {
     from {
        transform: scale(1)
     }
     to {
        transform: scale(1.05)
     }
 }
</style>