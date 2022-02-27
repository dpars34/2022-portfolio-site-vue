<template>
  <div class="navbar">
      <div class="navbar__container">
          <div :class="[isEnglish ? 'navbar__triangle' : 'navbar__triangle-japanese', clicked ? 'navbar__triangle-clicked' : '']">
                <div class="navbar__triangle-content" @click="handleClick">
                    <p v-if="isEnglish" class="navbar__triangle-text">日本語</p>
                    <p v-if="!isEnglish" class="navbar__triangle-text-japanese">English</p>
                    <div class="navbar__svg-container">
                    <svg width="100%" height="100%" viewBox="0 0 72 72" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M25.7701 49.77L39.5101 36L25.7701 22.23L30.0001 18L48.0001 36L30.0001 54L25.7701 49.77Z" :fill="isEnglish ? '#232323' : '#ececec'"/>
                    </svg>
                </div>
                </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name: 'Navbar',
    props: {
        isEnglish: {
            type: Boolean,
            default: true,
        } 
    },
    methods: {
        handleClick() {
            this.clicked = true
            this.$emit('handle-click', this.isEnglish)
        }
    },
    data() {
        return {
            clicked: false
        }
    }
}
</script>

<style>

.navbar__container {
    position: absolute;
    top: 0;
    right: 0;
}

.navbar__triangle {
    height: 0;
    width: 0;
    border-style: solid;
    border-width: 0 15rem 12rem 0;
    border-color: transparent #ececec transparent transparent;
    pointer-events: none;
}

.navbar__triangle-japanese {
    height: 0;
    width: 0;
    border-style: solid;
    border-width: 0 15rem 12rem 0;
    border-color: transparent #232323 transparent transparent;
    pointer-events: none;
}

.navbar__triangle:hover, .navbar__triangle-japanese:hover {
    animation: zoom-in 0.5s forwards
}

@keyframes zoom-in {
    from {
        border-width: 0 15rem 12rem 0;
    }
    to {
        border-width: 0 16rem 13rem 0;
    }
}

.navbar__triangle-clicked {
    border-width: 0 16rem 13rem 0;
}

.navbar__triangle-content {
    position: absolute;
    top: 1rem;
    right: 0rem;
    display: flex;
    align-items: center;
    pointer-events: auto;
}

.navbar__triangle-content:hover {
    cursor: pointer;
}

.navbar__triangle-text {
    font-size: 1.6rem;
    color: #232323;
    font-weight: 700;
}

.navbar__triangle-text-japanese {
    font-size: 1.6rem;
    color: #e1e1e1;
    font-weight: 700;
}

.navbar__svg-container {
    height: 3rem;
    width: 3rem;
}

</style>