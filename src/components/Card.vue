<template>
    <div class="card" :class="{ 'card__japanese' : !isEnglish }" @click="openLink(data.link)">
        <h3 class="card__title" :class="{ 'card__japanese-text' : !isEnglish }">{{ data.name }}</h3>
        <div class="card__image-container">
            <img class="card__image" :src="data.image" :alt="data.imageAlt">
        </div>
        <p class="card__text" :class="{ 'card__japanese-text' : !isEnglish }">{{ data.text }}</p>
        <p class="card__date" :class="{ 'card__japanese-text' : !isEnglish }">{{ data.date }}</p>
    </div>
</template>

<script>
export default {
    name: 'Card',
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
    methods: {
        openLink(url) {
            window.open(url, '_blank').focus()
        }
    }
}
</script>

<style scoped>
.card {
    border: solid 0.1rem #E1E1E1;
    border-radius: 50px;
    padding: 3.2rem;
}

.card:hover {
    cursor: pointer;
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
    aspect-ratio: 16/9;
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

.card__japanese {
    border: solid 0.1rem #e1e1e1;
    background-color: #f9f9f9;
}

.card__japanese-text {
    color: #232323
}

</style>