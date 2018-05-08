<template>
  <button type="button" 
    :aria-pressed="String(isPressed)"
    @click="handleClick">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: 'VicButton',

  props: {
    isPressed: {
      default: false,
      type: Boolean,
    },
    text: {
      default: '',
      type: String,
    }
  },

  methods: {
    handleClick (e) {
      let pressed = e.target.getAttribute('aria-pressed') === 'true'
      e.target.setAttribute('aria-pressed', String(!pressed))
    }
  }
};
</script>

<style lang="sass" scoped>
button
  background-color: #000
  border: none
  border-radius: 0.5rem
  color: white
  font-size: 18px
  font-weight: 700
  padding: 0.75em 1.5em

  &[aria-pressed]
    box-shadow: 0.125em 0.125em 0 #fff, 0.25em 0.25em #000
    left: -0.25rem
    position: relative
    top: -0.25rem

  &[aria-pressed="true"]
    box-shadow: inset 0 0 0 0.15rem #000, inset 0.25em 0.25em 0 #fff

  &[aria-pressed]:focus
    box-shadow: 0 0 0 0.25rem yellow
    outline: none

  &[aria-pressed="true"]:focus
    box-shadow: 0 0 0 0.25rem yellow, inset 0 0 0 0.15rem #000, inset 0.25em 0.25em 0 #fff


</style>