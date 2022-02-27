<template>
  <div class="line">
      <hr class="line__hr"/>
  </div>
</template>

<script>
export default {
    name: 'Line'
}
</script>

<style scoped>
.line {
    width: 100vw;
    display: flex;
    justify-content: center;
}
.line__hr {
    background-color: #DB9205;
    border: none;
    height: 0.2rem;
    width: 30rem;
    margin: 0;
}
</style>