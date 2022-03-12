<template>
    <div class="japanese-to-english-transition">
        <div class="transition__container">
            <div class="transition-triangle">
            </div>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.japanese-to-english-transition {
    height: 100vh;
    width: 100vw;
    overflow: hidden;
}

.transition-container {
    position: absolute;
    top: 0;
    right: 0;
}

.transition-triangle {
    border-style: solid;
    border-width: 0 13rem 13rem 0;
    border-color: transparent #232323 transparent transparent;
    animation: grow 1s forwards;
}

@keyframes grow {
    from {
        height: 0;
        border-width: 0 13rem 13rem 0;
    }
    to {
        height: 100vh;
        border-width: 0 120vw 120vw 0;
    }
}
</style>