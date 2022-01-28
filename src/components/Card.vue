<template>
  <div class="card">
      <h3 class="card__title">Onkun - The simple kanji dictionary</h3>
      <div class="card__image-container">
        <img class="card__image" src="@/assets/project1.png" alt="Onkun project">
      </div>
      <p class="card__text">OnKun is the simple kanji dictionary. It aims to display kanji readings in a simple and clear way, with on-yomi readings on the left in black, and kun-yomi readings on the right in red.</p>
      <p class="card__date">May 2021</p>
  </div>
</template>

<script>
export default {
    name: 'Card'
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