<template>
  <div class="to-japanese-transition">
  </div>
</template>

<script>

export default {
    name: "ToJapaneseTransition",
}
</script>

<style scoped>

.to-japanese-transition{
    height: 100vh;
    width: 100vw;
    background-image: linear-gradient(88deg, #232323 49.8%, #ececec 49.9%);
    font-family: 'Cabin', sans-serif;
    background-size: 250%;
    background-position: 50% 50%;
    animation: animation 1s forwards ease;
}

@keyframes animation {
    from {
        background-position: 50% 50%;
    }

    to {
        background-position: 100% 50%;
    }
}
</style>