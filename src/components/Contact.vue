<template>
  <div class="contact">
      <Header :text="data.title"/>
      <div class="contact__form-container">
          <form :action="sendMessage">
              <div class="contact__form-group">
                  <label class="contact__label" for="name">{{ data.name }}</label>
                  <input class="contact__input" name="name" type="text" autocomplete="off" required>
              </div>
              <div class="contact__form-group">
                  <label class="contact__label" for="email">{{ data.email }}</label>
                  <input class="contact__input" name="email" type="text" autocomplete="off" required>
              </div>
              <div class="contact__form-group">
                  <label class="contact__label" for="message">{{ data.message }}</label>
                  <textarea class="contact__textarea" name="message" type="text" autocomplete="off" required></textarea>
              </div>
              <div class="contact__button-container">
                <Button class="contact__button" :text="data.send"/>
              </div>
          </form>
      </div>
  </div>
</template>

<script>
import Header from '@/components/Header'
import Button from '@/components/Button'
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
    components: { Header, Button }
}
</script>

<style>
.contact {
    padding: 1.6rem;
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
    border: solid 0.3rem #e1e1e1;
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
    border: solid 0.3rem #e1e1e1;
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
}
</style>