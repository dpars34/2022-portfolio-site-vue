<template>
  <div class="card">
      <h3 class="card__title">{{ title }}</h3>
      <div class="card__image-container">
        <img class="card__image" :src="image" :alt="imageAlt">
      </div>
      <p class="card__text">{{ text }}</p>
      <p class="card__date">{{ date }}</p>
  </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        title: {
            type: String
        },
        image: {
            type: String
        },
        imageAlt: {
            type: String
        },
        text: {
            type: String
        },
        date: {
            type: String
        }
    }
}
</script>

<style scoped>
.card {
    width: 40rem;
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