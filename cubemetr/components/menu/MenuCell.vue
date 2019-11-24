<template>
  <div class="menuCell">
    <img :class="srcImg">
    <span v-text="item.name"></span>
  </div>
</template>

<script>
  export default {
    name: "MenuCell",
    props: {
        item: {}
    },
    computed: {
        srcImg() {
            return `menuCell__img img-${this.item.src}`
        }
    }
  }
</script>

<style lang="sass">
  .menuCell
    display: flex
    position: relative
    width: 600px
    color: white
    border: 5px solid green
    border-radius: 15px
    margin: 3%
    height: 350px
    justify-content: flex-end
    > span
      padding: 0 10px 10px 0
      align-self: flex-end
      font-size: 48px
      flex-basis: 100%
      text-align: right
      z-index: 1
      background-color: rgba(210, 105, 30, 0.5)
    &__img
      position: absolute
      width: 100%
      height: 100%
      background-repeat: no-repeat

  @media only screen and (max-width: 640px)
    .menuCell
      width: 300px
      height: 175px
      > span
        font-size: 24px
  @media only screen and (orientation: landscape) and (max-width: 1024px) and (min-width: 400px)
    .menuCell
      width: 300px
      height: 175px
      > span
        font-size: 24px
</style>
