<template>
  <div class="english-screen">
      <Card />
  </div>
</template>

<script>
import Card from '@/components/Card'
export default {
    name: 'English Screen',
    components: { Card }
}
</script>

<style>
.english-screen {
    height: 100vh;
    width: 100vw;
    background-color: #232323;
}
</style>