<template>
  <div class="contact">
      <Header :text="data.title" :isEnglish="isEnglish"/>
      <div class="contact__form-container">
          <form ref="form" @submit.prevent="sendEmail">
              <div class="contact__form-group">
                  <label class="contact__label" :class="{ 'contact__japanese-text': !isEnglish }" for="user_nam">{{ data.name }}</label>
                  <input class="contact__input" :class="{ 'contact__japanese-input': !isEnglish }" name="user_name" type="text" autocomplete="off" required>
              </div>
              <div class="contact__form-group">
                  <label class="contact__label" :class="{ 'contact__japanese-text': !isEnglish }" for="user_email">{{ data.email }}</label>
                  <input class="contact__input" :class="{ 'contact__japanese-input': !isEnglish }" name="user_email" type="text" autocomplete="off" required>
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
                alert("Message sent successfully!")
            }, (error) => {
                console.log(error.text)
                alert("Message could not be sent! "+error);
            })
        }
    }
}
</script>

<style scoped>
.contact {
    padding: 3.2rem 1.6rem;
    max-width: 1440px;
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
    color: #FFFFFF;
    background-color: #DB9205;
    border-radius: 10px;
}

.contact__japanese-text {
    color: #232323;
}

.contact__japanese-input {
    background-color: #F9F9F9;
    border: solid 0.1rem #e1e1e1;
}

@media screen and (min-width: 768px) {
  .contact {
    padding: 3.2rem 10rem;
  }
}
</style>