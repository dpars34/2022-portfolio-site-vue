<template>
  <div class="header">
            <svg width="50" height="50" viewBox="0 0 50 50" fill="none" xmlns="http://www.w3.org/2000/svg">
                <circle cx="25" cy="25" r="25" fill="#DB9205"/>
                <path d="M16 35.71L28.9798 25L16 14.29L19.996 11L37 25L19.996 39L16 35.71Z" :fill="color"/>
            </svg>
            <p class="header-text">{{ text }}</p>
        </div>
</template>

<script>
export default {
    name: 'Header',
    props: {
        text: {
            type: String,
            required: true
        },
        color: {
            type: String,
            default: '#232323'
        }
    }
}
</script>

<style scoped>
.header {
    display: flex;
    align-items: center;
}

.header-text {
    color: white;
    font-size: 7.2rem;
    font-family: 'Cabin', sans-serif;
    padding-left: 2rem;
    margin: 0;
}
</style>