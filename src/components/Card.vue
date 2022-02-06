<template>
  <div class="card">
      <h3 class="card__title">{{ data.name }}</h3>
      <div class="card__image-container">
        <img class="card__image" src="@/assets/project1.png" :alt="data.imageAlt">
      </div>
      <p class="card__text">{{ data.text }}</p>
      <p class="card__date">{{ data.date }}</p>
  </div>
</template>

<script>
import image1 from '@/assets/project1.png'

export default {
    name: 'Card',
    props: {
        data: {
            type: Object,
            required: true
        }
    },
    data() {
        return {
            image1: image1
        }
    }
}
</script>

<style scoped>
.card {
    border: solid 0.3rem #E1E1E1;
    border-radius: 50px;
    padding: 3.2rem;
}

.card__title {
    font-size: 2.4rem;
    color: #E1E1E1;
    margin: 0;
    margin-bottom: 3.2rem;
}

.card__image {
    height: 100%;
    width: 100%;
    object-fit: cover;
    border-radius: 10px;
}

.card__text {
    font-size: 1.6rem;
    color: #E1E1E1;
}

.card__date {
    font-size: 1.6rem;
    color: #E1E1E1;
    font-style: italic;
}
</style>