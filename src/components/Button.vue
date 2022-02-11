<template>
  <div class="button">
      <button class="button__button">{{ text }}</button>
  </div>
</template>

<script>
export default {
    name: 'Button',
    props: {
        text: {
            type: String,
            required: true
        }
    }
}
</script>

<style>
.button__button {
    all: unset;
    padding: 0.1em 1.5em;
    color: #FFFFFF;
    background-color: #DB9205;
    border-radius: 10px;
}
</style>